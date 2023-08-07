<template>
  <div class="card">
    <button @click="$emit('favoritar', id)">Favoritar</button>
    <span v-if="favorito">Favorito</span>
    <img
      :width="120"
      src="https://media.istockphoto.com/id/635948926/pt/foto/3d-rendering-of-antibiotic-pills-in-blister-pack.jpg?s=612x612&w=is&k=20&c=k-JRRiTDW7emwQOPiVOPNEK-K3MBxEi9zy3i2jAM19o="
      alt="imagem do medicamento"
    />
    <span>Nome: {{ nome }}</span>
    <span>Laboratório: {{ laboratorio }}</span>
    <span>Preço: {{ preco }}</span>
  </div>
</template>

<script >
export default {
  props: ["nome", "laboratorio", "preco", "favorito", "id"],
};
</script>

<style scoped>


.card {
  display: flex;
  flex-direction: column;
  width: 100%/4 - 2em;
  margin: 1em;
  background-color: #c4c4c4;
}
</style>