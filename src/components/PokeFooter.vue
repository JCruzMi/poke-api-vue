<template>

    <ul class="list-group">
        <li class="list-group-item d-flex justify-content-between align-items-center">
            <span class="badge badge-dark badge-pill">HP</span>
            <div class="progress" style="width:70%">
                <div class="progress-bar bg-danger" role="progressbar" :style="{width: poke.hp+'%'}">{{poke.hp}}/300</div>
            </div>
        </li>
        <li class="list-group-item d-flex justify-content-between align-items-center">
            <span class="badge badge-dark badge-pill">ATK</span>
            <div class="progress" style="width:70%">
                <div class="progress-bar bg-warning" role="progressbar" :style="{width: poke.atk+'%'}">{{poke.atk}}/300</div>
            </div>
        </li>
        <li class="list-group-item d-flex justify-content-between align-items-center">
            <span class="badge badge-dark badge-pill">DEF</span>
            <div class="progress" style="width:70%">
                <div class="progress-bar bg-info" role="progressbar" :style="{width: poke.def+'%'}">{{poke.def}}/300</div>
            </div>
        </li>
        <li class="list-group-item d-flex justify-content-between align-items-center">
            <span class="badge badge-dark badge-pill">ESP ATK</span>
            <div class="progress" style="width:70%">
                <div class="progress-bar bg-success" role="progressbar" :style="{width: poke.espatk+'%'}" aria-valuenow="25" aria-valuemin="0" aria-valuemax="150">{{poke.espatk}}/300</div>
            </div>
        </li>
        <li class="list-group-item d-flex justify-content-between align-items-center">
            <span class="badge badge-dark badge-pill">ESP DEF</span>
            <div class="progress" style="width:70%">
                <div class="progress-bar bg-success" role="progressbar" :style="{width: poke.espdef+'%'}" aria-valuenow="25" aria-valuemin="0" aria-valuemax="150">{{poke.espdef}}/300</div>
            </div>
        </li>
        <li class="list-group-item d-flex justify-content-between align-items-center">
            <span class="badge badge-dark badge-pill">EXP</span>
            <div class="progress" style="width:70%">
                <div class="progress-bar bg-success" role="progressbar" :style="{width: poke.exp}" aria-valuenow="25" aria-valuemin="0" aria-valuemax="150">{{poke.espdef}}/1000</div>
            </div>
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
}

.badge{
    width: 5rem;
    padding: .3rem 1rem;
}

</style>