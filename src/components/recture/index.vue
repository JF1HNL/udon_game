<template>
  <div>
    <h1>recture</h1>
    <input type="button" value="go to top" @click="page = PAGE_NAME.top" >
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