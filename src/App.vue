<template>
  <div id="app">
    <h1>Guia clientes</h1>
    <Cliente :cliente="clienteVictor"/>
    <Cliente nome="Benj" idade="25" descricao="FullStrack" email="bneto@computacao" numero="123456"/>
    <Cliente nome="Bf" idade="25" descricao="FullStrack" email="bneto@computacao" numero="123456"/>
    <hr>
    <input type="text" v-model="clienteVictor.nome">
    <input type="text" v-model="clienteVictor.email">
    <input type="text" v-model="clienteVictor.descricao">
    <hr>
    <h4>
      lista de produtos
    </h4>
    <hr>
    <Produto/>
  </div>
  
</template>

<script>

import Cliente from './components/Cliente'
import Produto from './components/Produto'

export default {
  name: 'App',
  data(){
    return{
      nomeCLiente:"Benjamim",
      clienteVictor:{
        nome:"ChernoBen",
        email:"bneto@computacao",
        idade:"25"

      }
    }
  },
  components:{
    Cliente,
    Produto
    
  }
  
}
</script>

<style>
#app {
  
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color:green;
  margin-top: 60px;
}
</style>
