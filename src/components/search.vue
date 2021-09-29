<template>
  <div class="container">
    <h2>Filtro de nombres</h2>
    <section>
      <form v-on:submit.prevent="onSubmit">
        <input
          type="text"
          placeholder="Buscador de nombres"
          id="inputName"
          v-model="valSearch"
        />
        <button @click="setSearch">Buscar</button>
      </form>
    </section>
  </div>
</template>
<script>
export default {
  name: "search",
  data() {
    return {
      valSearch: "",
    };
  },
  methods: {
    setSearch() {
      let searchToUpperCase = this.valSearch.toUpperCase();
      this.$emit("passSearch", searchToUpperCase);
      this.valSearch = "";
    },
  },
};
</script>
<style scoped>
.container {
  display: flex;
  flex-direction: column;
  background: rgb(64, 179, 179);
  margin: 0.5rem;
  padding-bottom: 1rem;
}
h2 {
  padding: 0;
}

input {
  height: 1rem;
  padding: 2px;
  margin-right: 0.5rem;
}
button {
  background-color: transparent;
  height: 24px;
  color: whitesmoke;
}
button:hover {
  color: black;
}
</style>
