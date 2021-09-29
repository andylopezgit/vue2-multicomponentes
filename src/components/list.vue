<template>
  <div class="container">
    <h2>Listado de nombres</h2>
    <ul>
      <li v-for="(item, $index) in cleanList" :key="$index">{{ item }}</li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "list",
  props: ["fromAdd", "valSearch"],

  data() {
    return {
      valor: "andres",
    };
  },

  computed: {
    cleanList() {
      if (this.valSearch === "") {
        return this.fromAdd;
      } else {
        return this.fromAdd.filter((name) => name === this.valSearch);
      }
    },
  },
};
</script>
<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-content: center;
  background: cadetblue;
  min-height: 100px;
  margin: 0;
  padding: 1rem;
}
h2 {
  margin: 0;
  padding: 0;
}
ul {
  margin: 10px;
  padding: 0;
  list-style: none;
}

li {
  margin: 0;
  padding: 0;
  list-style: none;
}
</style>
