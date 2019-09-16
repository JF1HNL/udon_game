<template>
  <div @click="udon_click()" :class="{ not : !display_flag }">
    <div>
      <img :src="url" class="child geted" :class="{ not : !display_flag }">
    </div>
  </div>
</template>

<style>
img.not {
  opacity: 0;
}
img.geted {
  filter: grayscale(100%);
}
div.not {
  background-color: blueviolet;
}
</style>

<script>
export default {
  props: [
    'geted_flag',
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