<template>
  <ul class="list-group" :v-if="pokes">
      
      <Item :pokes="pokes"/>
  </ul>
</template>

<script>
import Item from './Item.vue'
export default {
    components:{
        Item
    },
    props:['pokes']
}
</script>

<style>

</style>