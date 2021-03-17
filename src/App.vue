<template>
  <div id="app">
    <h1>Guia clientes</h1>
    <Cliente :cliente="clienteVictor" :showIdade="true" :showNome="true"/>
    <hr>
    <div v-for="(cliente,index) in clientes" :key="cliente.id">
      <h1>{{index + 1}}</h1>
      <Cliente :cliente="cliente" :showIdade="true" :showNome="true"/>
      <hr>
      <h4>edit</h4>
      <input type="text" v-model="cliente.nome">
      <input type="text" v-model="cliente.email">

    </div>
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

      },
      clientes:[
        {
          id:1,
          nome:"Benj",
          email:"benj@comp",
          idade:"25"
        },
        {
          id:2,
          nome:"Bnj",
          email:"chernoBen@comp",
          idade:"25" 
        },
        {
          id:3,
          nome:"Bj",
          email:"cB@comp",
          idade:"25" 
        }
      ]
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
