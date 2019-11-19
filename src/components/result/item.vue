<template>
  <div class="item_parent">
    <div class="item">
      <div>{{ result_item.date }}</div>
      <img :src="url_maker(result_item.img)" alt="">
      <div v-for='(it, i) in result_item.menu' :key=i>
        <div v-if="length_judge(it.name)">
          <div class="long">
            {{ it.name }}
          </div>
          <div class="left">
            {{ it.price }}円
          </div>
        </div>
        <div v-else>{{ it.name }}：{{ it.price }}円</div>
      </div>
    </div>
  </div>
</template>

<style>
.item_parent {
  display: flex;
}
.item{
  background-color: #BDC085;
  border: 2px solid #b6694b;
  border-radius: 10px;
  font-size: 5vmin;
  margin: 1vh auto;
  padding: 2vmin;
}
.long {
  white-space: nowrap;
}
.left {
  text-align: right;
}
</style>

<script>
export default {
  props: [
    'result_item',
    'id'
  ],
  methods :{
    length_judge: function(e){
      if(e.length > 12){
        return true;
      }
      return false;
    },
    url_maker: function(e){
      return `https://www.instagram.com/p/${e}/media/?size=m`
    }
  }
}
</script>