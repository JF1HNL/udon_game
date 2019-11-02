<template>
  <div>
    <h1>結果発表！</h1>
    <ol>
      <li v-for='(it, i) in result_ary' :key=i>{{ it.menu[0].name }}</li>
    </ol>
    <input type="button" value="top" @click="page(PAGE_NAME.top)" >
  </div>
</template>

<script>
import {PAGE_NAME} from '../../const.js'

export default {
  props: [
    'result_ary'
  ],
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