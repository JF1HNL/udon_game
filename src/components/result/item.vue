<template>
  <div>
    <ul>
      <li>{{ id }}</li>
      <ul>
        <li v-for='(it, i) in result_item.menu' :key=i>{{ it.name }}：{{ it.price }}円</li>
      </ul>
    </ul>
  </div>
</template>

<script>
export default {
  props: [
    'result_item',
    'id'
  ]
}
</script>