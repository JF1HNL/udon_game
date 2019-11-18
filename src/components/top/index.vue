<template>
  <div>
    <div class='title'>udon-game</div>
    <div>
      <input type="button" value="遊び方" ontouchstart=”” @click="page(PAGE_NAME.recture)" >
    </div>
    <div>
      <input class='start' type="button" ontouchstart=”” value="ゲームスタート！" @click="page(PAGE_NAME.game)" >
    </div>
    <div>
      <Insta/>
    </div>
  </div>
</template>

<style>
.title{
  font-size: 15vmin;
  margin-top: 20vh;
  font-weight: 700;
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