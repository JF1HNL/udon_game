<template>
  <div>
    <div class="result_title">結果発表</div>
    <div class='geted_udon'>ゲットしたうどん一覧</div>
    <div v-for='(it, i) in result_ary' :key=i>
      <item  :result_item=it :id=i />
    </div>
    <div class="sum">合計{{ sum_price }}円</div>
    <input type="button" value="top" @click="page(PAGE_NAME.top)" >
  </div>
</template>

<style>
  .result_title{
    font-size: 9vmin;
    font-weight: 700;
    margin-top: 2vh;
  }
  .geted_udon, .sum {
    font-size: 5vmin;
  }
</style>

<script>
import {PAGE_NAME} from '../../const.js'
import item from './item.vue'

export default {
  props: [
    'result_ary'
  ],
  components: {
    item
  },
  computed: {
    sum_price: function(){
      let ret = 0;
      for(let i in this.result_ary){
        for(let j in this.result_ary[i].menu){
          ret += this.result_ary[i].menu[j].price
        }
      }
      return ret;
    }
  },
  data: function() {
    // PAGE_NAME
    return {
      PAGE_NAME
    }
  },
  methods: {
    page: function(){
      this.$emit(PAGE_NAME.top)
    }
  }
}
</script>