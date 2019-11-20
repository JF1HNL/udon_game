<template>
  <div id="app">
    <top 
      v-if="page_judge(PAGE_NAME.top)"
      v-on:recture='page_chenge(PAGE_NAME.recture)'
      v-on:game='page_chenge(PAGE_NAME.game)'
    />
    <recture 
      v-if="page_judge(PAGE_NAME.recture)"
      v-on:top='page_chenge(PAGE_NAME.top)'
    />
    <game 
      v-if="page_judge(PAGE_NAME.game)" 
      v-on:receive='result_receive'
    />
    <result
      v-if="page_judge(PAGE_NAME.result)"
      :result_ary="result_ary"
      v-on:pricesent='result_price'
      v-on:top='page_chenge(PAGE_NAME.top)'
    />
    <formcompornent
      v-if="page_judge(PAGE_NAME.form)"
      :price="price"
      v-on:page='page_chenge'
    />
    <rankigncompornent/>
  </div>
</template>

<script>
import top from './components/top/index.vue'
import recture from './components/recture/index.vue'
import game from './components/game/index.vue'
import result from './components/result/index.vue'
import formcompornent from './components/form/index.vue'
import rankigncompornent from './components/ranking/index.vue'

import {PAGE_NAME} from './const.js'
// import test from './const.js'

import {insta_data} from './components/game/data.js'

export default {
  name: 'app',
  components: {
    top,
    recture,
    game,
    result,
    formcompornent,
    rankigncompornent
  },
  data: function(){
    return {
      PAGE_NAME,
      result_ary: insta_data,
      price: -1,
      page: 'top'
    }
  },
  methods: {
    result_receive: function(ary){
      this.result_ary = ary;
      this.page_chenge(PAGE_NAME.result);
    },
    result_price: function(num){
      this.price = num;
      this.page_chenge(PAGE_NAME.form);
    },
    page_judge: function(e){
      if(this.page === e){
        return true
      }
      return false
    },
    page_chenge: function(e){
      window.scrollTo(0, 0);
      this.page = e;
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Sawarabi+Gothic&display=swap&subset=japanese');
body{
  background-color: #C5AE45;
}
#app {
  font-family: 'Sawarabi Gothic', sans-serif;
  text-align: center;
  color: #7D5B93;
  margin:0;
  padding: 0;
}

input, button {
  margin: 2vmax;
  font-size: 4vmax;
  display: inline-block;
  text-align: left;
  border: 2px solid #b6694b;
  color: #b6694b;
  background-color: #C6BA85;
  text-decoration: none;
  font-weight: bold;
  padding: 2vmin 8vmin;
  text-align: center;
  border-radius: 4px;
  -webkit-appearance: none;
}

input:active, button:active {
  background-color: #b6694b;
  border-color: #b6694b;
  color: #C6BA85;
}
</style>
