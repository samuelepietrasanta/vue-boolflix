<template>
  <div>
    <div id="app" class="d-flex">
      <input v-model="filmUtente" type="text" placeholder="Inserisce il nome del film">
      <button @click='Stampa()' class="btn btn-primary"> prova </button>
    </div>


    <div>
      <h2>{{prova}}</h2>
    </div>

    <ul>
      <li></li>
    </ul>

  </div>
</template>

<script>
import axios from 'axios'


export default {
  name: 'App',
  components: {
  },
  data(){
    return{
      prova: '',
      filmUtente : '',
    }
    

  },

  /* mounted(){
    axios.get('https://api.themoviedb.org/3/search/movie?api_key=403992ffc6869ff17454611af19a8ef3&query' + this.filmUtente)
    .then((risposta =>{
      this.prova = risposta.data.results[0].adult;

    }))
  }, */

  methods: {  
    Stampa(){
      axios.get('https://api.themoviedb.org/3/search/movie?api_key=403992ffc6869ff17454611af19a8ef3&query=' + this.filmUtente)
      .then((risposta =>{
      this.prova = risposta.data.results[0].id;}))
        console.log(this.filmUtente)
      }

  }

  }
</script>

<style lang="scss">

@import '~bootstrap/dist/css/bootstrap.min.css';
#app {
  justify-content: center;
}
</style>
