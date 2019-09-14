<template>
  <div>
    <h1>game</h1>
    <input type="button" value="result" @click="page(PAGE_NAME.result)" >
    <Img v-for='(it, i) in insta_data' :key='i' :display_flag="true" :url="url_maker(it.img)" :position="123"/>
  </div>
</template>

<script>
import {PAGE_NAME} from '../../const.js'
import Img from './image.vue'
import {insta_data} from './data.js'


export default {
  components: {
    Img
  },
  data: function() {
    // PAGE_NAME
    return {
      insta_data,
      PAGE_NAME
    }
  },
  methods: {
    page: function(){
      this.$emit(PAGE_NAME.result)
    },
    url_maker: function(e){
      return `https://www.instagram.com/p/${e}/media/?size=m`
    }
  }
}
</script>