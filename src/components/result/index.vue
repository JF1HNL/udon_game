<template>
  <div>
    <h1>result</h1>
    <input type="button" value="top" @click="page(PAGE_NAME.top)" >
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
      this.$emit(PAGE_NAME.top)
    }
  }
}
</script>