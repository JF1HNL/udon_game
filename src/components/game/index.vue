<template>
  <div>
    <h1>game</h1>
    <input type="button" value="result" click="page()" >
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
    page: function(){
      this.$emit(PAGE_NAME.result)
    }
  }
}
</script>