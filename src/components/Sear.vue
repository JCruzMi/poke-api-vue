<template>  
    <form @submit.prevent="filtrar">
        <div class="container">
    
            <div style="width:100%">
                <input
                    type="text"
                    class="form-control my-3"
                    placeholder="Buscar pokemon"
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

<style>
.img{
    width: 5%;
    height: 5%;
}
</style>