<template>
  <div id="app">
    <div class="searchbar">
      <input v-model="filmUtente" type="text" placeholder="Inserisce il nome del film">
      <button @click='stampa()' class="btn btn-primary"> prova </button>
    </div>

    <ul>
      <li><Film  v-for="(film,index) in tuttiIFilm" :key="index" 
                :title="film.title" :original_title="film.original_title"
                :original_language="film.original_language" :vote="film.vote_average" /> </li>
    </ul>

  </div>
</template>

<script>
import axios from 'axios'
import Film from './components/Film.vue'


export default {
  name: 'App',
  components: {
    Film
  },
  data(){
    return{
      filmUtente : '',
      tuttiIFilm : []
    }
  },

  methods: {  
    stampa(){
      axios.get('https://api.themoviedb.org/3/search/movie' , {
        params:{
          api_key:'403992ffc6869ff17454611af19a8ef3',
          query: this.filmUtente

        }
      })
      .then(risposta =>{
      this.tuttiIFilm = risposta.data.results.slice()
      console.log(this.tuttiIFilm) })
        
      console.log(this.filmUtente);
        
      }

  }

  }
</script>

<style lang="scss">

@import '~bootstrap/dist/css/bootstrap.min.css';

#app{
  ul{
    li{
      list-style-type: none;
    }
  }

  .searchbar {
  display: flex;
  justify-content: center;
  margin-bottom: 50px;
}

}


</style>
