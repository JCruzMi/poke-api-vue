<template>

    <ul class="list-group">
        <li class="list-group-item d-flex justify-content-between align-items-center">
            <span class="badge badge-dark badge-pill">HP</span>
            <div class="progress" >
                <div class="progress-bar bg-danger" role="progressbar" :style="{width: poke.hp+'%'}"></div>
            </div>
            <span class="data">{{poke.hp}}</span>
        </li>
        <li class="list-group-item d-flex justify-content-between align-items-center">
            <span class="badge badge-dark badge-pill">ATK</span>
            <div class="progress" >
                <div class="progress-bar bg-warning" role="progressbar" :style="{width: poke.atk+'%'}"></div>
            </div>
            <span class="data">{{poke.atk}}</span>
        </li>
        <li class="list-group-item d-flex justify-content-between align-items-center">
            <span class="badge badge-dark badge-pill">SPD</span>
            <div class="progress" >
                <div class="progress-bar bg-warning" role="progressbar" :style="{width: poke.speed+'%'}"></div>
            </div>
            <span class="data">{{poke.speed}}</span>
        </li>
        <li class="list-group-item d-flex justify-content-between align-items-center">
            <span class="badge badge-dark badge-pill">DEF</span>
            <div class="progress" >
                <div class="progress-bar bg-info" role="progressbar" :style="{width: poke.def+'%'}"></div>
            </div>
            <span class="data">{{poke.def}}</span>
        </li>
        <li class="list-group-item d-flex justify-content-between align-items-center">
            <span class="badge badge-dark badge-pill">SP. ATK</span>
            <div class="progress" >
                <div class="progress-bar bg-success" role="progressbar" :style="{width: poke.espatk+'%'}" aria-valuenow="25" aria-valuemin="0" aria-valuemax="150"></div>
            </div>
            <span class="data">{{poke.espatk}}</span>
        </li>
        <li class="list-group-item d-flex justify-content-between align-items-center">
            <span class="badge badge-dark badge-pill">SP. DEF</span>
            <div class="progress" >
                <div class="progress-bar bg-success" role="progressbar" :style="{width: poke.espdef+'%'}" aria-valuenow="25" aria-valuemin="0" aria-valuemax="150"></div>
            </div>
            <span class="data">{{poke.espdef}}</span>
        </li>
        <li class="list-group-item d-flex justify-content-between align-items-center">
            <span class="badge badge-dark badge-pill">EXP</span>
            <div class="progress">
                <div class="progress-bar bg-success" role="progressbar" :style="{width: poke.exp}"></div>
            </div>
            <span class="data">{{poke.exp}}</span>
            
        </li>
    </ul>
    
    
    
</template>

<script>

export default {
    props:['poke'],
    setup(){
        
    }
}
</script>

<style scoped>

.list-group-item{
    background: transparent;
    border: transparent;
    padding-top: 1rem;
}

.badge{
    width: 5rem;
    padding: .3rem 1rem;
}

.progress{
    margin-left: 1rem;
    width:70%;
    height:20px;
}

.data{
    width: 2.5rem;
    padding-left: 0.3rem;
    font-weight: bold;
}

.progress-bar{
    padding: 0rem 0.5rem;
    text-align: center;
    color: black;
    height: 20px;
}

</style>