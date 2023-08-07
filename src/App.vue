<template>
  <Header> </Header>

  <FormularioNovoMedicamento @cadastrarNovoMedicamento="AdicionarMedicamento">
  </FormularioNovoMedicamento>
  <div class="container">
    
    <CardMedicamento
      v-if="!!listaMedicamentos"
      v-for="medicamento in listaMedicamentos"
      :key="medicamento.id"
      @favoritar="favoritarMedicamento"
      :nome="medicamento.nome"
      :laboratorio="medicamento.laboratorio"
      :preco="medicamento.preco"
      :id="medicamento.id"
    />
  </div>
</template>

<script >
import { v4 as uuidv4 } from "../node_modules/uuid";

import Header from "./components/Header.vue";

import FormularioNovoMedicamento from "./components/FormularioNovoMedicamento/index.vue";

import CardMedicamento from "./components/CardMedicamento/index.vue";

export default {
  components: {
    Header,
    FormularioNovoMedicamento,
    CardMedicamento,
  },

  data() {
    return {
      listaMedicamentos: [],
    };
  },
  methods: {
    AdicionarMedicamento(nome, laboratorio, preco) {
      if (nome === "" || laboratorio === "" || preco === 0) {
        alert("Preencha todos os dados");
        return;
      }
      const novoMedicamento = {
        id: uuidv4(),
        nome: nome,
        laboratorio: laboratorio,
        preco: preco,
        favorito: false
      };
      this.listaMedicamentos.push(novoMedicamento);
    },
    favoritarMedicamento(id) {
      this.listaMedicamentos.map((item) => {
        if (item.id == id) {
          item.favorito = !item.favorito;
        }
      });
    },
  },
};
</script>
 

<style scoped>
.container {
  display: flex;
  flex-wrap: wrap;
  width: 100vw;
  padding: 1em;
}
</style>
