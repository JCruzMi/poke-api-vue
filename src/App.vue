<template>
  <div class="container">
    <img class="im" src="https://ianars.github.io/Pok-dex/images/pokedeex.png">
    <poke-app2></poke-app2>
  </div>
</template>

<script>
import PokeApp2 from './components/PokeApp2.vue';

export default {
  name: "App",
  components: {
    PokeApp2
    
  }
};
</script>

<style>

::-webkit-scrollbar {display: none;}

body{ 
  height: 100%; 
  margin-top: 3%;
  background-color: #065A9C;
 }

.container .im{
  width: 50%;
  margin-top: -2rem;
  margin-bottom: 1rem;
}
 
#app {
  font-family: "Segoe UI";
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}
</style>
