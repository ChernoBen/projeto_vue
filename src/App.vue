<template>
  <div id="app">
    <h3>Cadastro</h3>
    <input type="text" placeholder="nome" v-model="nomeField"><br>
    <input type="email" placeholder="email" v-model="emailField"><br>
    <input type="number" placeholder="idade" v-model="idadeField">
    <button @click="cadastrarUsuario">Cadastrar</button>
    <hr>
    <h1>Guia clientes</h1>
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

      nomeField:"",
      emailField:"",
      idadeField:0,
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
        }
      ]
    }
  },
  components:{

    Cliente,
    Produto
    
  },
  methods:{

    cadastrarUsuario:function(){
      if(this.nomeField == "" || this.nomeField=="" || this.nomeField < 3){
        console.log("erro validação")
      }
      this.clientes.push({

        nome:this.nomeField,
        email:this.emailField,
        idade:this.idadeField,
        id:Date.now()

      })
      this.nomeField = "" ;
      this.emailField = "" ;
      this.idadeField = 0 ;
    }
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
