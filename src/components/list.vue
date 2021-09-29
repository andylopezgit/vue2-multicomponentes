<template>
  <div class="container">
    <h2>Component List</h2>
    <ul>
      <li v-for="(item, $index) in cleanList" :key="$index">{{ item }}</li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "list",
  props: ["fromAdd","valSearch"],
  
  data() {
    return {
        valor: 'andres',
    };
  },

  computed: {
    cleanList() {
        if (this.valSearch === '') {
            return this.fromAdd
        } else {
            return this.fromAdd.filter((name) => name === this.valSearch);
        }
    
      
      
    },
  },
};
</script>
<style scoped>
.container {
  background: cadetblue;
  height: 200px;
  margin: 1rem;
  padding: 1rem;
}

li {
  list-style: none;
}
</style>
