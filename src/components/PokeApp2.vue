<template>
    <div v-if="pokes">
        <Suspense>
        <template #default>
            <poke-list2></poke-list2>
        </template>
        <template #fallback>
            Cargando...
        </template>
        </Suspense>
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

        const Color = {
          normal : '#ffe175',
          fighting : '#ff6200',
          flying:'#008db0',
          ground: '#7f724a',
          rock: '#908a78',
          bug: '#85b100',
          steel:'#c5c5c5',
          fire:'#ff9000',
          water:'#00c3c7',
          grass: '#abff4d',
          electric: '#fffd4d',
          psychic:'#613dfe',
          ice:'#97cdff',
          dragon:'#ff335c',
          dark:'#323232',
          fairy:'#ff7af3',
          unknown:'#ffb9b9',
          shadow:'#757575',
          ghost: '#8d1bdb',
          poison: '#690081'
        }
        provide("Color",Color)
        
        const mHeader = ref(true)
        provide('mHeader',mHeader)

        watchEffect(() => {
            for (let i = 1; i<= 898; i++){
                axios.get('https://pokeapi.co/api/v2/pokemon/'+i)
                .then( response => {

                    let aux = response.data.types

                    let pk = {
                        'name':response.data.name, 
                        'id':response.data.id, 
                        'img':response.data.sprites.other["official-artwork"].front_default,
                        'atk':response.data.stats[1].base_stat, 
                        'hp':response.data.stats[0].base_stat, 
                        'espatk':response.data.stats[3].base_stat,
                        'def':response.data.stats[2].base_stat,
                        'espdef':response.data.stats[4].base_stat,
                        'speed':response.data.stats[5].base_stat,
                        'height':response.data.height,
                        'weight':response.data.weight,
                        'type2':"",
                        'types': response.data.types[0].type.name,
                        'exp':response.data.base_experience,
                        'bg':{background : Color[response.data.types[0].type.name]},
                        'bg2':"",
                        'stats': false
                    }
                    
                    if (aux.length>=2){
                        pk["type2"] = (aux[1].type["name"])
                        pk["bg2"] = ({background :Color[aux[1].type["name"]]})
                    }
                
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