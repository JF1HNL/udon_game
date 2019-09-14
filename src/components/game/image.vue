<template>
  <div>
    <div v-if="display_flag">
      <img :src="url" @click="udon_click()">
    </div>
  </div>
</template>

<script>
export default {
  props: [
    'display_flag',
    'url'
  ],
  methods: {
    udon_click: function(){
      this.$emit('select')
    }
  }
}
</script>