<template>
  <div @click="udon_click()" class="function_div" :class="{ not : !display_flag, geted: !geted_flag}">
    <div>
      <img :src="url" class="child" :class="{ not : !display_flag, geted : geted_flag}">
    </div>
  </div>
</template>

<style>
.function_div{
  border: 2px solid #b6694b;
}
img.not {
  opacity: 0;
}
img.geted {
  filter: grayscale(100%);
}
div.not { 
  background-color: #C6BA85;
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