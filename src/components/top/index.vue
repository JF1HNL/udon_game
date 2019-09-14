<template>
  <div>
    <div>udon-game</div>
    <div>
      <input type="button" value="遊び方" @click="page(PAGE_NAME.recture)" >
    </div>
    <div>
      <input type="button" value="ゲームスタート！" @click="page(PAGE_NAME.game)" >
    </div>
    <div>
      <Insta/>
    </div>
  </div>
</template>

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