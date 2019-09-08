<template>
  <div>
    <h1>game</h1>
    <input type="button" value="result" @click="page = PAGE_NAME.result" >
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