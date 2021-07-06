<template>
    <stats :poke="poke" v-if="poke.stats"/>
    
    <div class="col-6 col-sm-6 col-md-3 col-lg-3 col-xl-3"  v-if="mHeader">
        <div class="card-container" type="button"  @click="onStatsClick(poke.id)">
            <div class="card" :style="poke.bg">
                <div class="front">
                    <div class="poke">
                        <img :src="poke.img">
                    </div>
                    <div class="card-body">
                        <span class="pokename d-flex justify-content-between">
                            <span>#{{poke.id}}</span>
                            <span>{{poke.name}}</span>
                        </span>
                    </div>
                </div>      
            </div>
        </div>
    </div>
  
</template>

<script>
import {inject} from 'vue'
import Stats from './Stats.vue'
export default {
  components: { Stats },
    props:['poke'],
    setup(){

        const pokes = inject('pokes')

        const mHeader = inject('mHeader')

        const onStatsClick = id => {
            mHeader.value = false
            pokes.value = pokes.value.map(item => {
                if(item.id === id){
                    item.stats = !item.stats
                }
                
                return item
            })
        }
        return {onStatsClick, mHeader}
    }
}
</script>

<style scoped>

.card-container{
    display:flex;
    align-items: center;
    justify-content: center;
}

.card{
    margin-top: 2rem ;
    border-radius: 20px;
    height: 120px;
    width: 157px;
    border: 0px;
    position: relative;
    background: rgb(231,63,202);
    background: linear-gradient(225deg, rgba(231,63,202,1) 0%, rgba(184,30,180,1) 73%);
}

.pokename{
    padding: 0.3rem 1rem;
    border-radius: 20px;
    background-color:black;
    color: white;
    display: block;
    margin-top: 0.5rem;
    opacity: 0.75;
    font-weight: bold;
    font-size: 11px;
    text-transform: capitalize;
}

.pokename span:last-child{
    display: inline-block;
}

.pokename span:first-child{
    margin-right: 0.5rem;
    color:rgb(209, 57, 201);
    display: inline-block;
}


.poke{
    position: absolute;
    width: 100%;
    display: block;
    margin-top: -20px;
    position: relative;
}

img{
    height: 60px;
    width: auto;
}


</style>