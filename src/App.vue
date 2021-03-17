<template>
  <div id="app">
    <h1>Guia clientes</h1>
  </div>
  
</template>

<script>
import Cliente from './components/Cliente.vue'
// import Cliente from './components/Cliente.vue'
export default {
  name: 'App',
  components:{
    Cliente
    
  }
  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
