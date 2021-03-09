<template>
    <div class="container">
        <div class="poke-card">
            <div class="unkown">
                <div class="card" :style="poke.bg" type="button"  @click="onStatsClick(poke.id)">
                    <div class="pokemon" >
                        <img :src="poke.img" alt="" width="92" height="92">
                    </div>
                    <div class="card-body" >
                        <span>{{poke.name}}</span>
                        <div class="peso">
                            <ul class="list-group">
                                <li class="list-group-item d-flex justify-content-between align-items-center">
                                    {{poke.height}}
                                    <span>{{poke.weight}}</span>
                                </li> 
                                <li class="list-group-item d-flex justify-content-between align-items-center">
                                    Altura
                                    <span>Peso</span>
                                </li> 
                            </ul>
                        </div>
                        <br>
                    
                        <poke-footer :poke="poke"></poke-footer>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

import {inject} from 'vue'
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

        return {onStatsClick}
    }
}
</script>

<style scoped>
.pokedex{
    z-index: 1;
    margin-left: auto;
  margin-right: auto;
    position: relative;

}

.onePoke{
    
    margin-left: 36.5%;
    margin-top: 65px;
    z-index: 3;
    
    position: absolute;
}

.info{
    z-index: 3;
    
    position: absolute;
    margin-left: 30.5%;
    margin-top: 28%;
    width: 320px;
    
}

.poke-card {
    margin-top: 10rem;
    width: 100%;
    text-align: center;
    justify-content: center;
    align-items: center;
    display: flex;
  
}

.card{
        width: 400px;
        height: 120px;
    }

.card-body{
        width: 100%;
    }

.list-group{
    background: transparent;
}

.list-group-item{
    background: transparent;
    border: transparent;
}
.pokemon{
        margin-top: 5%;
    }
    
.container{
    color:#fff;
    width: 600px;
}
</style>