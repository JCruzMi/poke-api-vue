<template>
    <div :v-if="pokes">
        <poke-list2></poke-list2>
    </div>
</template>

<script>
import PokeList2 from './PokeList2.vue'
import axios from 'axios'
import {ref, provide, watchEffect} from 'vue'

export default {
    components: {
        PokeList2
    },
    setup(){
        const pokes = ref([])

        watchEffect(() => {
            for (let i = 1; i<= 150; i++){
                axios.get('https://pokeapi.co/api/v2/pokemon/'+i)
                .then( response => {
                    let pk= {'id':response.data.id,'name':response.data.name, 'img':response.data.sprites.other.dream_world.front_default, 'atk':response.data.stats[1].base_stat, 'hp':response.data.stats[0].base_stat, 'esp':response.data.stats[3].base_stat ,'def':response.data.stats[2].base_stat}

                    pokes.value.push(pk)
                }).catch( e => console.log(e))
            }
        })
        provide('pokes',pokes)

        return {pokes}
    }
   
    
}
</script>

<style>

</style>