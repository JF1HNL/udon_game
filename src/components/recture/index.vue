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
      <div class="recture_child_body">最後に揃えたうどんの値段がスコアとして表示されます。より高いスコアを目指そう！</div>
    </div>
    <div class="recture_parent">
      <div class="recture_child_title">お手つきを20回したら終了！</div>
      <div class="recture_child_body">ゲームをスタートすると上部にお手つきの残り回数が表示されます！それが0になったらゲーム終了です。</div>
    </div>
    <div class="recture_parent">
      <div class="recture_child_title">ランキングに登録しよう！</div>
      <div class="recture_child_body">
        <div>GETしたスコアはランキングに登録することができます。</div>
        <div>目指せ！ランク1位!</div>
        <rankbutton/>
      </div>
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
.recture_child_body, .recture_child_body > div {
  font-size: 2.5vmax;
  font-weight: 500;
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
import rankbutton from '../parts/ranking.vue'

export default {
  components: {
    Insta,
    Twitter,
    rankbutton
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