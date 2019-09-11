<template>
  <div>
    <h1>udon-game</h1>
    <input type="button" value="recture" click="page(PAGE_NAME.recture)" >
    <input type="button" value="game" click="page(PAGE_NAME.game)" >
  </div>
</template>

<script>
import {PAGE_NAME} from '../../const.js'

export default {
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