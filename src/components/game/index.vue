<template>
  <div>
    <h1>game</h1>
    <input type="button" value="result" @click="page(PAGE_NAME.result)" >
    <Img :display_flag="true" :url="PAGE_NAME"/>
  </div>
</template>

<script>
import {PAGE_NAME} from '../../const.js'
import Img from './image.vue'

export default {
  components: {
    Img
  },
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