<template>
  <div>
    <input type="button" value="Twitterはこちら！" ontouchstart=”” @click="go_twitter()">
  </div>
</template>

<style scoped>
input {
  margin: 2vmax;
  font-size: 3vmax;
  display: inline-block;
  text-align: left;
  border: 2px solid #b6694b;
  color: #b6694b;
  background-color: #C6BA85;
  text-decoration: none;
  font-weight: bold;
  padding: 2vmin 5vmin;
  border-radius: 4px;
  -webkit-appearance: none;
}

input:active {
  background-color: #b6694b;
  border-color: #b6694b;
  color: #C6BA85;
}
</style>

<script>
export default {
  methods: {
    go_twitter: function(){
      location.href = 'https://www.twitter.com/jf1hnl/'
    }
  }
}
</script>