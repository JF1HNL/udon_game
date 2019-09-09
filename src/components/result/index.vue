<template>
  <div>
    <h1>result</h1>
    <input type="button" value="top" click="page()" >
  </div>
</template>

<script>
import PAGE_NAME from '../../const.js'

export default {
  props: {
    PAGE_NAME
  },
  data: function() {
    // PAGE_NAME
    return {
      
    }
  },
  methods: {
    page: function(){
      this.$emit(PAGE_NAME.top)
    }
  }
}
</script>