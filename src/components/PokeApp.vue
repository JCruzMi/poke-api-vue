<template>
    <div :v-if="pokes">
        <poke-list :pokes="pokes"></poke-list>
    </div>
</template>

<script>
import PokeList from './PokeList.vue'
import axios from 'axios'

export default {
    components: {
        PokeList
    },
    data(){
        return{
            pokes : [],
        }
    },
    created(){
        this.getPokes()
    },
    methods: {
        getPokes(){
            axios.get('https://pokeapi.co/api/v2/pokemon/1')
            .then( response => {
                this.pokes = response.data
                //this.formatPost(response.data)
            }).catch( e => console.log(e))
        
        },
        getPokesAll(){
            for (let i = 1; i<= 2; i++){
                axios.get('https://pokeapi.co/api/v2/pokemon/'+i)
                .then( response => {
                    this.pokes = response.data
                    //this.formatPost(response.data)
                }).catch( e => console.log(e))
            }
        },
        formatPost(posts){
            for (let key in posts){
                this.pokes.push({ ...posts[key],id:key })
            }
            console.log(this.pokes)
        },
       
    },
    
}
</script>

<style>

</style>