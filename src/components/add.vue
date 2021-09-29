<template>
  <div class="container">
    <form v-on:submit.prevent="onSubmit">
      <input type="text" placeholder="Ingrese su nombre" v-model="task" />
      <button @click="addTask">Agregar</button>
    </form>
  </div>
</template>
<script>
export default {
  name: "add",
  data() {
    return {
      task: "",
      tasks: [],
    };
  },
  methods: {
    addTask() {
      let toUpperCase = this.task.toUpperCase();
      this.tasks.push(toUpperCase);
      this.$emit("emitAdd", this.tasks);
      this.task = "";
    },
  },
};
</script>
<style scoped>
.container {
  display: flex;
  flex-direction: row;
  justify-items: center;
  justify-content: center;
  background-color: darkcyan;
  margin-top: 0.5rem;
  padding: 1rem;
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
