<template>
  <div>
    <h1>game</h1>
    <input type="button" value="result" @click="page(PAGE_NAME.result)" >
    <input type="button" value="元に戻すボタン" @click="uragaesu()">
    <div v-for='(udon_ary_, j) in udon_ary' :key='j' class="parent">
      <Img
        v-for='(it, i) in udon_ary_'
        :key='i'
        :display_flag="it.display_flag"
        :geted_flag="it.geted_flag"
        :url="url_maker(it.data.img)"
        @select='udon_click(it)'
        class="child"
      />
    </div>
  </div>
</template>

<style>
  .parent {
    display: flex;
    justify-content: space-around;
  }
  .child {
    height: 18.75vw;
    width: 25vw;
  }
</style>


<script>
import {PAGE_NAME} from '../../const.js'
import Img from './image.vue'
import {insta_data} from './data.js'


export default {
  mounted: function(){
    this.shuffle_data();
    this.geted_object_position_id = [];
  },
  computed: {
    select_udon_ary: function(){
      return this.udon_ary.flat().filter(udon => udon.display_flag && !udon.geted_flag)
    },
    geted_udon_ary: function(){
      return this.udon_ary.flat().filter(udon => udon.geted_flag)
    }
  },
  components: {
    Img
  },
  data: function() {
    // PAGE_NAME
    return {
      udon_ary: [],
      message: '',
      click_object: {},
      PAGE_NAME
    }
  },
  methods: {
    page: function(){
      this.$emit(PAGE_NAME.result)
    },
    url_maker: function(e){
      return `https://www.instagram.com/p/${e}/media/?size=m`
    },
    shuffle_data: function(){
      // 全データから6つの番号を取得する
      const get_six_data = function(){
        const return_ary = [];
        for(let i = 0; i < 6; i++){
          while(true){
            const random_num = Math.floor(Math.random() * insta_data.length)
            // 判定
            for(let j in return_ary){
              if(return_ary[j] === random_num){
                continue;
              }
            }
            return_ary.push(random_num);
            break;
          }
        }
        return return_ary;
      }
      // 0~5の番号を二回使って場所を決める
      const select_position = function(){
        const FIRST_NUM = -1;
        let return_ary = [[],[],[],[]];
        // FIRST_NUMをセット
        for(let i in return_ary){
          let n = 3;
          while(n){
            return_ary[i].push(FIRST_NUM);
            n--;
          }
        }
        // 0~11までの値をそれぞれセット
        let i = 11;
        while(i + 1){
          let a = Math.floor(Math.random() * 4);
          let b = Math.floor(Math.random() * 3);
          if(return_ary[a][b] > FIRST_NUM){continue;}
          return_ary[a][b] = i;
          i--; 
        }
        // 全ての値を2でわる
        for(let i in return_ary){
          for(let j in return_ary[i]){
            return_ary[i][j] = Math.floor(return_ary[i][j] / 2)
          }
        }
        return return_ary;
      }
      // 最後にそれぞれのobjectをセットする
      let return_ary = [[], [], [], []];
      const get_num_data_ary = get_six_data();
      const select_position_ary = select_position();
      for(let i in select_position_ary){
        for(let j in select_position_ary[i]){
          return_ary[i].push({
            data: insta_data[
              get_num_data_ary[
                select_position_ary[i][j]
              ]
            ],
            position_id : [i,j],
            geted_flag : false,
            display_flag : false
          })
        }
      }
      this.udon_ary = return_ary;
    },
    uragaesu: function(){
      for(let i in this.select_udon_ary){
        this.select_udon_ary[i].display_flag = false;
      }
    },
    udon_click: function(e){
      if(e.geted_flag && e.display_flag){
        return
      }
      e.display_flag = true;
      const con = this.udon_ary.flat().filter(it => it.data.img === e.data.img);
      if(con[0].display_flag && con[1].display_flag){
        con[0].geted_flag = true;
        con[1].geted_flag = true;
      }
    }
  }
}
</script>