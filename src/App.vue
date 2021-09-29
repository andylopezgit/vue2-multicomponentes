<template>
  <div id="app">
    <section class="header">
      <h2>Practica Vue 2</h2>
      <h4>Comunicacion entre 3 componentes hijos</h4>
      <img alt="Vue logo" src="./assets/logo.png" id="logo">
    </section>
    
    
    <list :fromAdd="fromAdd" :valSearch="valSearch"/>
    <add @emitAdd="getAdd"/>
    <search @passSearch="setValSearch"/>
  </div>
</template>

<script>
import list from "@/components/list.vue"
import search from "@/components/search.vue"
import add from "@/components/add.vue"

export default {
  name: 'App',
  components: {
    list, add, search
  },
  data() {
    return {
      fromAdd: [],
      valSearch: ''
    }
    },
    methods: {
      getAdd (val) {
        this.fromAdd = val
      },

      setValSearch (val) {
        this.valSearch = val
      }
  },

  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
  background: rgb(224, 214, 214);
}

#logo {
  width:50px;
}

.header {
  margin: 0 0;
  padding: 1px;
}
</style>
