<template>
  <div>
    <div class='title'>udon-game</div>
    <div class="howtoplay">遊び方</div>
    <div class="sub_title">
      <div>「udon-game」は</div>
      <div>うどんの画像を使った神経衰弱です！</div>
    </div>
    <div class="recture_parent">
      <div class="recture_child_title">
        <div>より高い値段の</div>
        <div>うどんをGETしよう！</div>
      </div>
      <div class="recture_child_body">最後に揃えたうどんの値段が表示されます。より高い値段を目指そう！</div>
    </div>
    <div class="recture_parent">
      <div class="recture_child_title">手数制限があります！</div>
      <div class="recture_child_body">ゲームをスタートすると上部に手数が表示されます！手数が0になったらゲーム終了です。</div>
    </div>
    <div class="recture_parent">
      <div class="recture_child_title">このゲームについて</div>
      <div class="recture_child_body">
        <div>ここに表示されるうどんの画像は作者が実際に食べたうどんの画像です。</div>
        <div>これらの画像はInstagramやTwitterにのっています。</div>
        <div>よかったらチェックしてみてください！</div>
        <Insta/>
        <Twitter/>
      </div>
    </div>
    <input type="button" value="戻る" @click="page(PAGE_NAME.top)" >
  </div>
</template>

<style>
.howtoplay {
  font-size: 5vmax;
  font-weight: 600;
}
.sub_title {
  font-size: 5vw;
  margin: 2vh 0;
}
.recture_parent {
  border: 2px solid #b6694b;
  margin: 2vh 5vw;
  padding: 2vmin;
  border-radius: 5vmin;
}
.recture_child_title {
  font-size: 3.5vmax;
}
.recture_child_body {
  font-size: 2.5vmax;
}
</style>

<style scoped>
  .title {
    margin-top: 0;
  }
</style>


<script>
import {PAGE_NAME} from '../../const.js'
import Insta from '../parts/insta.vue'
import Twitter from '../parts/twitter.vue'

export default {
  components: {
    Insta,
    Twitter
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