<template >
  <div :class="{'cliente':!isPremium,'cliente-premium':isPremium}">
    <h4 v-show="showNome == true">Nome: {{cliente.nome }}</h4>
    <hr>
    <p>{{cliente.descricao}}</p>
    <hr>
    <p>Número:{{cliente.numero}}</p>
    <hr>
    <p>Email:{{cliente.email | processarEmail}}</p>
    <hr>
    <p v-if="showIdade == true"> idade:{{cliente.idade}}</p>
    <p v-else>Idade escondida com sucesso</p>
    <h4>Id especial: {{idEspecial}} </h4>
    <button @click="mudarCor">Mudar cor</button>
    <button @click="emitirEventoDelete">deletar</button>
  </div>
</template>

<script>
export default {
    //data binding de 1 caminho (one way) " :value='valor' "
    data(){

        return {

            isPremium:false
        }
    },
    props:{

        showNome:Boolean,
        showIdade:Boolean,
        cliente:Object

    },
    methods:{

        mudarCor:function(){
            //eventos retornam dados

            this.isPremium = !this.isPremium

        },
        emitirEventoDelete:function(){
            console.log("Emitido do filho!")
            //this.$emit("meDelete",{curso:"Vue.js",emPromocao:true,component:this})
        }
        
    },
    filters:{
        processarEmail:function(value){
            //altera dados de uma variavel em um elemento
            return "CHERNOBEN " + value.toUpperCase();
        }
    },
    computed:{
        idEspecial:function(){
            return (this.cliente.email + this.cliente.nome + this.cliente.id).toUpperCase();
        }

    }

}
</script>

<style scoped>

.cliente{

    color:#5e3d34;
    background-color: #ECE5E3;
    max-width: 600;
    height: 300;
    padding: 1%;
    margin-top: 2%;
   
}
.cliente-premium{
    background-color: black;
    color: yellow;
    max-width: 600px;
    padding: 1%;
    margin-top: 2%;
}

</style>