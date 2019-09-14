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
      v-on:result='page_chenge(PAGE_NAME.result)'
    />
    <result
      v-if="page_judge(PAGE_NAME.result)"
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
      page: 'top'
    }
  },
  methods: {
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
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
