<template>
    <div class="container">
        <div class="poke-card">
            <div class="card" :style="poke.bg" type="button"  @click="onStatsClick(poke.id)">
                <div class="top-card d-flex justify-content-between">
                    <span v-if="poke.id<10">#00{{poke.id}}</span>
                    <span v-if="poke.id>=10 && poke.id<100">#0{{poke.id}}</span>
                    <span v-if="poke.id>=100">#{{poke.id}}</span>
                    <span>{{poke.name}}</span>
                </div>
                <div class="pokemon" >
                    <img :src="poke.img" alt="" height="130">
                </div>
                <div class="card-body" >
                    <div class="type">
                        <span :style="poke.bg">{{poke.types}}</span>
                        <span v-if="poke.type2" :style="poke.bg2">{{poke.type2}}</span>
                    </div>
                    <poke-footer :poke="poke"></poke-footer>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

import { inject } from 'vue'
import PokeFooter from './PokeFooter.vue'

export default {
props: ["poke"],
    components:{
        PokeFooter 
    },  
    setup(){
         const pokes = inject('pokes')

         const mHeader = inject('mHeader')

        //cambia el valor stats para mostrar o no dando click al boton los elementos 
        const onStatsClick = id => {
            mHeader.value = true
            pokes.value = pokes.value.map(item => {
                if(item.id === id){
                    item.stats = !item.stats
                }
                return item
            })
        }

        return { onStatsClick }
    }
}
</script>

<style scoped>

.poke-card {
    margin-top: 6rem;
    width: 100%;
    text-align: center;
    justify-content: center;
    align-items: center;
    display: flex;
}

.card{
    border: 0px;
    border-radius: 20px;
    max-width: 400px;
    min-width: 345px;
    height: 135px;
}

.top-card{
    margin-top: -1.7rem;
    display: block;
    font-weight: bold;
    font-size: 16px;
    color: black;
    text-transform: capitalize;
}

.top-card span:first-child{
    color:rgb(209, 57, 201);
}

.card-body{
    width: 100%;
    padding-top: 3.5rem;
}

.card-body .type{
    font-size: 16px;
    color: white;
    display: flex;
    justify-content: center;
    width: calc(156px*2);
}

.card-body span{
    padding-top: 6px;
    width: 156px;
    height: 40px;
    background-color: rgba(48, 48, 48, 0.493);
    border-radius: 10px;
    text-transform: capitalize;
    
}

.card-body span:first-child{
    margin-left: -1rem;
    margin-right: 1rem;
}

.card-body span:last-child{
    margin-right: -1rem;
    margin-left: 1rem;
}




.list-group{
    background: transparent;
}

.list-group-item{
    background: transparent;
    border: transparent;
}
.pokemon{
    width: 100%;
    display: block;
    margin-top: -2rem;
    position: relative;
}
</style>