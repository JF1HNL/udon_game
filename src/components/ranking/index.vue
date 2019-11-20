<template>
  <div>
    <div>ranking</div>
  </div>
</template>

<script>
export default {
  mounted: function(){
    fetch('https://script.google.com/macros/s/AKfycbwOTB3-XX5bm0kcnyWQrgDPyC1w_bx9wf9lSVaFu2yW8td84Drc/exec', {mode: 'cors'})
    .then(res => res.json())
    .then(
    result => {
      this.data = result
    },
    error => {
      console.log("errorらしい")
    })
  },
  data: function(){
    return {
      data_ary:[]
    }
  }
}
</script>