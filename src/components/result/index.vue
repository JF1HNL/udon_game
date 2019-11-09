<template>
  <div>
    <h1>結果発表！</h1>
    <div v-for='(it, i) in result_ary' :key=i>
      <item  :result_item=it :id=i />
    </div>
    <input type="button" value="top" @click="page(PAGE_NAME.top)" >
  </div>
</template>

<script>
import {PAGE_NAME} from '../../const.js'
import item from './item.vue'

export default {
  props: [
    'result_ary'
  ],
  components: {
    item
  },
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