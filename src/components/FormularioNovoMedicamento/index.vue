<template>
 
    <div >
<h2>Formulário de Cadastro de Medicamento</h2>

        <label for="nome">Nome</label>
        <input type="text" id="nome" placeholder="Nome do medicamento" v-model="medicamento">
        <label for="laboratorio">Laboratório</label>
        <input type="text" id="laboratorio" placeholder="Nome do laboratório" v-model="laboratorio">
        <label for="preco">Preço</label>
        <input type="text" id="preco" placeholder="Informe o preço" v-model="preco">
        <button @click="$emit('cadastrarNovoMedicamento',medicamento, laboratorio, preco)">Cadastrar novo</button>
        
    </div>

    
</template>

<script >

export default{

data(){
    return {
    medicamento:"",
    laboratorio:"",
    preco: 0
    }
  }
  }
</script>
 

<style scoped>

</style>