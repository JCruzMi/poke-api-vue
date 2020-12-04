<template>
  <div class="col-sm-6 col-md-4 col-xl-3"  :v-if="poke.length">
      <div class="card-container">
      <div class="card">
          <div class="front">
            <div class="cover">
              <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAQ0AAAC8CAMAAABVLQteAAAAA1BMVEX/ZgAqRcUWAAAASElEQVR4nO3BAQ0AAADCoPdPbQ43oAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAC+DcZIAAF57zC0AAAAAElFTkSuQmCC" alt="">
            </div>
            <div class="poke">
				  <img class ="img-circle" :src="poke.img">
			</div>
          <div class="card-body" >
              <li class="list-group-item d-flex justify-content-between align-items-center">
                <span>
                    {{poke.name}}
                </span>
                <span>
                    {{poke.hp}}  Hp
                </span>
            </li>
                
          </div>
          </div>
          <div class="card-footer">
            <li class="list-group-item d-flex justify-content-between align-items-center bg-dark text-white">
                <span>
                    ATK
                    <br>
                    {{poke.atk}}
                </span>
                <span>
                    DEF
                    <br>
                    {{poke.def}}
                </span>
                <span>
                    ESP
                    <br>
                    {{poke.esp}}
                </span>
            </li>  
        </div>      
          </div>
      </div>
  </div>
  
</template>

<script>
export default {
    props:['poke'],
    setup(){
        
    }
}
</script>

<style>
.card .cover img{
    width: 80%;
    margin-top: 10% ;
    background: #cec150;
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
}

.card .card-footer{
    margin-bottom: 5%;
}

.card{
    margin-bottom: 10%;
}
</style>