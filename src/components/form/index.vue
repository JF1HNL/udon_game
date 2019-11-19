<template>
  <div>
    <h1>aaa</h1>
      <form action="https://docs.google.com/forms/u/0/d/e/1FAIpQLSdB3FvmSEcXI_LUr4PZm__IKmDYM-gNvVABDwhIRdg4fbzk5g/formResponse">
        <label for="test1">test1</label>
        <input type="text" id="test1" name="entry.494011733" :value="price" readonly="readonly">
        <label for="test2">test2</label>
        <input id="test2" name="entry.304301637" type="text" placeholder="お気軽にお問い合わせください。" value="aaa">
        <button type="submit" name="button" value="送信"></button>
      </form>
  </div>
</template>

<style scoped>

</style>

<script>
export default {
  props: [
    'price'
  ],
  data: function(){
    return {
      
    }
  }
}
</script>