<template>
  <div>
    <udongametitle/>
    <div v-if="!!(price + 1)">
      <div class="subtitle">ランキング登録フォーム</div>
      <form :action="action_url">
        <label>今回のスコア</label>
        <input type="text" name="entry.494011733" :value="price" readonly="readonly" class="notactive display">
        <label>ニックネームを</label>
        <label >記入してください</label>
        <input name="entry.304301637" type="text" placeholder="ニックネーム" value="通りすがりのうどんマニア" class="display">
        <button :type="{ submit : send_button_flag }" name="button" value="送信" @click="msg++">
          <font>送信</font>
        </button>
      </form> 
      <input type="button" value="結果ページに戻る" @click="page(PAGE_NAME.result)">
    </div>
    <input type="button" value="最初から" @click="page(PAGE_NAME.top)"> 
  </div>
</template>

<style scoped>
input.display{
  width: 75vw;
  margin: 1vh auto 2vh;
  padding: 2vmin;
  text-align: center;
  font-size: 6vmin;
  border: 4px solid #b6694b;
}
.notactive:active {
  background-color: #C6BA85;
  border-color: #b6694b;
  color: #b6694b;
}
label{
  margin: 0;
  font-size: 6vmin;
}
.subtitle {
  margin: 3vmin 0;
  font-size: 7vmin;
}
form {
  text-align: center;
  display: flex;
  flex-direction: column;
  justify-content: center;
  border: 4px solid #b6694b;
  padding: 3vmin;
  background: #C6BA85;
  margin: 3vmin;
  border-radius: 20px;
}
</style>

<script>
import udongametitle from '../parts/udon_game.vue'
import {PAGE_NAME} from '../../const.js'

export default {
  props: [
    'price'
  ],
  components:{
    udongametitle
  },
  mounted: function(){
    this.button_hide(true);
  },
  data: function(){
    return {
      send_button_flag: true,
      msg: 0,
      PAGE_NAME,
      action_url: 'https://docs.google.com/forms/u/0/d/e/1FAIpQLSdB3FvmSEcXI_LUr4PZm__IKmDYM-gNvVABDwhIRdg4fbzk5g/formResponse'
    }
  },
  methods: {
    button_hide : function(e){
      this.send_button_flag = e;
    },
    page: function(e){
      this.$emit('page', e);
    },
    send_form: function(e){

    }
  }
}
</script>