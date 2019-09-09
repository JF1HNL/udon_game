<template>
  <div>
    <h1>recture</h1>
    <input type="button" value="go to top" click="page()" >
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