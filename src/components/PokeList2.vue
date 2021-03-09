<template>

    <sear v-if="mHeader"></sear>

  <div class="row" :v-if="pokes">
      <item v-for="poke in pokes"
        :key="poke.id"
        :poke="poke"></item>
  </div>
</template>

<script>
import {inject, provide, computed, ref} from 'vue'
import Item from './Item.vue'
import Sear from './Sear.vue'

export default {
    components:{
        Item,
        Sear
    },
    setup(){
        const AllPokes = inject('pokes')

        const estado = ref('')

        const mHeader = inject('mHeader')

        const pokes = computed(() => {
          if(estado.value === ''){
            return AllPokes.value
          }else{
            return AllPokes.value.filter(item => item.id === estado.value-1+1 || item.name.includes(estado.value))
          }
        })

        provide('estado', estado)

        return {pokes, mHeader}
    }
}
</script>

<style>

</style>