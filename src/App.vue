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
      v-on:top='page_chenge(PAGE_NAME.top)'
    />
  </div>
</template>

<script>
import top from './components/top/index.vue'
import recture from './components/recture/index.vue'
import game from './components/game/index.vue'
import result from './components/result/index.vue'

import {PAGE_NAME} from './const.js'
// import test from './const.js'


export default {
  name: 'app',
  components: {
    top,
    recture,
    game,
    result
  },
  data: function(){
    return {
      PAGE_NAME,
      result_ary: [],
      page: 'top'
    }
  },
  methods: {
    result_receive: function(ary){
      this.result_ary = ary;
      this.page_chenge(PAGE_NAME.result);
    },
    page_judge: function(e){
      if(this.page === e){
        return true
      }
      return false
    },
    page_chenge: function(e){
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
  color: #B6694A;
  margin:0;
  padding: 0;
}
</style>
