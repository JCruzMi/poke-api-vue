<template>
  <div class="container">
    <h1>PokeApi</h1>
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

body{ 
  height: 100%; 
  background: #3a3737; 
  margin-top: 5%;
 }
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: rgb(116, 92, 92);
  margin-top: 60px;
}
</style>
