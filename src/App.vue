<template>
  <div id="app">
    <h1>top</h1>
    <top v-if="page_judge(PAGE_NAME.top)" :page='page'/>
    <recture v-if="page_judge(PAGE_NAME.recture)" :page='page'/>
    <game v-if="page_judge(PAGE_NAME.game)" :page='page'/>
    <result v-if="page_judge(PAGE_NAME.result)" :page='page'/>
  </div>
</template>

<script>
import top from './components/top/index.vue'
import recture from './components/recture/index.vue'
import game from './components/game/index.vue'
import result from './components/result/index.vue'

import PAGE_NAME from './const.js'

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
      if(this.data.page === e){
        return true
      }
      return false
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
