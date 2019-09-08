<template>
  <div>
    <h1>result</h1>
    <input type="button" value="top" @click="page = PAGE_NAME.top" >
  </div>
</template>

<script>
import PAGE_NAME from '../../const.js'

export default {
  props: ['page'],
  data: function() {
    PAGE_NAME
  }
}
</script>