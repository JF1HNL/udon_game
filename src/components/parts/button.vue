<template>
  <div>
    <input type="button" value="インスタグラムへのリンクはこちら" @click="go_insta()">
  </div>
</template>

<script>
export default {
  methods: {
    go_insta: function(){
      location.href = 'https://www.instagram.com/jf1hnl/'
    }
  }
}
</script>