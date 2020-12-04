<template>
  <div class="row" :v-if="pokes">
      <item v-for="poke in pokes"
        :key="poke.id"
        :poke="poke"></item>
  </div>
</template>

<script>
import { inject } from 'vue'
import Item from './Item.vue'

export default {
    components:{
        Item

    },
    setup(){
        const pokes = inject('pokes')
        
        

        return {pokes}
    }
}
</script>

<style>

</style>