<template>
  <div id="app">
     <h1>{{tituloAPP}}</h1>
    
     <FrmCadProjeto/> 
     
  </div>
</template>

<script>
import FrmCadProjeto from "./components/FrmCadProjeto.vue"


export default {
  name: 'App',
  components: {
    FrmCadProjeto
  },

  data() {
    return {
       tituloAPP: "Projetos"
    }
  },
  methods: {

    
  }
}
   
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
