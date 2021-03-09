<template>
    <stats :poke="poke" v-if="poke.stats"/>

    <div class="col-sm-6 col-md-4 col-xl-3"  v-if="mHeader">
      <div class="card-container" type="button"  @click="onStatsClick(poke.id)">
      <div class="card">
          <div class="front">
            <div class="cover" :style="poke.bg">
            </div>
            <div class="poke">
				  <img class ="img-circle" :src="poke.img" alt="" width="92" height="92">
			</div>
          <div class="card-body" >
              <li class="list-group-item align-items-center">
                <span class="pokename">
                    {{poke.name}}
                </span>
                
            </li>
                
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
.card .cover{
    width: 100%;
    margin-top: -1px ;
    height: 120px;
    border-radius: 125px 125px 0px 0px;
    
    
}
.card .poke{
    border-radius: 50%;
    display: block;
    height: 125px;
    margin: -55px auto 0;
    overflow: hidden;
    width: 120px;
}
.card .poke img{
    background: none repeat scroll 0 0 #FFFFFF;
    border: 10px solid #FFFFFF;
    width: 100%;
}
.card .card-body{
    margin-top: -10%;
    background: transparent;
    border-color:transparent;
}

.card .card-body .pokename{
    color: #000;
    font-size: 20px;
    background: transparent;
}

.card .card-body .list-group-item{
    background: transparent;
    border-color:transparent;
}

.card .card-footer{
    margin-bottom: 5%;
    background: transparent;
}

.card{
    
    margin-bottom: 10%;
    border-radius: 100%;
}
</style>