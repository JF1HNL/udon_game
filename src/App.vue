<template>
  <div id="app">
    
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import top from './components/top/index.vue'
import recture from './components/recture/index.vue'
import game from './components/game/index.vue'
import result from './components/result/index.vue'

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
      page: 0
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
