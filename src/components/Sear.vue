<template>  
    <form @submit.prevent="filtrar">
        <div class="container">
            <div class="pokeball">
                <img src="https://icon-library.com/images/pokemon-ball-icon/pokemon-ball-icon-28.jpg" alt="24" width="42">
            </div>
            <div class="input">
                <input
                    type="text"
                    class="form-control my-3"
                    placeholder="Buscar Pokémon"
                    v-model.trim="texto"
                >
            </div>
        
        
        </div>
  </form>
</template>

<script>

import {ref, inject} from 'vue'

export default {
    setup(){
        const estado = inject('estado')
        
        const texto = ref('')

        const filtrar = () =>{
            if(texto.value === ''){
                estado.value = ''
            }
            else{
                estado.value = texto.value
            }
        }
        //return de la funcion que se usa en el componente
        return {filtrar, texto}

    }
}
</script>

<style scoped>

.container{
    display: flex;
    justify-content: between;
    align-items: center;
    padding: 0;
}

.pokeball{
    display: inline-block;
}
.input{
    display: inline-block;
    width: calc(100% - 50px);
}  

input{
    background-color: rgb(223, 223, 223);
    text-align: center;
    border-radius: 20px;
    border: 0px;
    font-weight: bold;
}
</style>