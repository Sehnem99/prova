<template>
  <div class="cadastro">
    <form @submit.prevent="salvarProjeto">
        <legend>Cadastro de Projetos </legend>
           <br>
           <br>
          <label>Nome: </label>
          <input type="text" id="nomePr" name="nomePr" placeholder="Informe o nome " v-model="projeto.nome"/>
           <br>
           <br>
          <label>Area: </label>  
          <select v-model="projeto.area">
            <option  placeholder="Informe o area" v-for="area in areasteste"  :key="area"> {{ area.text }} </option>
          </select>
           <br> 
           <br>
          <label>Prazo: </label>  
          <input class="Input" type="number" id="prazo" name="prazo"  placeholder="Informe o prazo" v-model="projeto.prazo" />
           <br> 
           <br>
          <label>Valor: </label>  
          <input type="text" id="valor" name="valor" placeholder="Informe o valor" v-model="projeto.valor"/>
           <br> 
           <br>
          <button id="btnAdicionar" @click="salvarProjeto()" type="submit">Adicionar Projeto</button>  


          {{projeto.valor}}
    </form>
  </div>
</template>

<script>


import axios from 'axios'


export default {
  name: 'FrmCadProjeto',
  data(){
    return{
        areasteste:
        [ 
          { text: 'TECNOLOGICA', value: 'TECNOLOGICA' },
          { text: 'HUMANA', value: 'HUMANA' },
          { text: 'MEDICA', value: 'MEDICA' }
        ],
        projeto: {
          nome: '',
          area: '',
          prazo:'',
          valor: 0
        }
    }
  },
  methods: {
    retornaGet () {
      axios
        .get('https://projeto-prova.herokuapp.com/projeto/')
        .then(response => (this.projetosGet = response))
    },
    
    salvarProjeto (){
      let JsonProjeto = JSON.parse(JSON.stringify(this.projeto))
      console.log(JsonProjeto)
      console.log('https://projeto-prova.herokuapp.com/projeto', this.projeto)
      axios.post('https://projeto-prova.herokuapp.com/projeto', this.projeto)
        /*Fazer a atualização do dastbord */
    },

    created(){
       /*Fazer a atualização do dastbord */
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
