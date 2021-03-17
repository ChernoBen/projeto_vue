<template>
  <div id="cliente">
    
    <input type="text" :value="nome">
    <input type="text" v-model="nome">
    <hr>
    <input type="text" :value="descricao"> 
    <input type="text" v-model="descricao">  
    <h2>Cada componente so pode ter uma tag raiz!</h2>
    <h2>{{ nome }}</h2>
    <h2>{{ descricao }}</h2>
  </div>
</template>

<script>
export default {
    //data binding de 1 caminho (one way) " :value='valor' "
    data(){

        return {

            nome:"Benjamim Francisco",
            numero:"",
            email:"",
            idade:0,
            descricao:"Full Stack"
        }
    }
}
</script>

<style scoped>

#cliente{

    color:green;
    background-color:black;
    max-width: 600;
    height: 300;
   
}
#cliente-nome{

    color:aliceblue;
    
}

</style>