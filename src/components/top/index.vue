<template>
  <div>
    <div class='title'>udon-game</div>
    <div>
      <input type="button" value="遊び方" @click="page(PAGE_NAME.recture)" >
    </div>
    <div>
      <input class='start' type="button" value="ゲームスタート！" @click="page(PAGE_NAME.game)" >
    </div>
    <div>
      <!-- <Insta/> -->
    </div>
  </div>
</template>

<style>
.title{
  font-size: 7vmax;
  margin-top: 25vh;
  font-weight: 700;
}
input {
  margin: 2vmax;
  font-size: 4vmax;
  display: inline-block;
  text-align: left;
  border: 2px solid #b6694b;
  color: #b6694b;
  text-decoration: none;
  font-weight: bold;
  padding: 2vmin 8vmin;
  border-radius: 4px;
  transition: .4s;
}

input:hover {
  background-color: #b6694b;
  border-color: #b6694b;
  color: #C6BA85;
}
</style>

<script>
import Insta from '../parts/button.vue'
import {PAGE_NAME} from '../../const.js'

export default {
  components: {
    Insta
  },
  data: function() {
    // PAGE_NAME
    return {
      PAGE_NAME
    }
  },
  methods: {
    page: function(e){
      this.$emit(e)
    }
  }
}
</script>