<template>
  <div>
    <div class='title'>
      <udongametitle/>
    </div>
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

<style scoped>
.title{
  margin-top: 20vh;
}
</style>

<script>
import Insta from '../parts/insta.vue'
import udongametitle from '../parts/udon_game.vue'
import {PAGE_NAME} from '../../const.js'

export default {
  components: {
    Insta,
    udongametitle
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