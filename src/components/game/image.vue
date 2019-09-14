<template>
  <div>
    <div v-if="display_flag">
      <img :src="url" @click="udon_click(position)">
    </div>
  </div>
</template>

<script>
export default {
  props: [
    'display_flag',
    'url',
    'position'
  ],
  methods: {
    udon_click: function(position){
      this.$emit(position)
    }
  }
}
</script>