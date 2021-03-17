<template >
  <div id="cliente">
    <h4>Nome: {{cliente.nome}}</h4>
    <hr>
    <p>{{cliente.descricao}}</p>
    <hr>
    <p>Número:{{cliente.numero}}</p>
    <hr>
    <p>Email:{{cliente.email}}</p>
    <hr>
    <p>idade:{{cliente.idade}}</p>
  </div>
</template>

<script>
export default {
    //data binding de 1 caminho (one way) " :value='valor' "
    // data(){

    //     return {

    //         numero:"123456",
    //         email:"bneto@comp.ufmt.cua.br",
    //         idade:25,
    //         descricao:"Full Stack developer"
    //     }
    // },
    props:{
        
        nome:String,
        numero:String,
        email:String,
        idade:String,
        descricao:String,
        cliente:Object
    }
}
</script>

<style scoped>

#cliente{

    color:#5e3d34;
    background-color: #ECE5E3;
    max-width: 600;
    height: 300;
    padding: 1%;
    margin-top: 2%;
   
}


</style>