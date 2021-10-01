<template>
  <div class="card">

   <h4>TITOLO : {{title}}</h4>
   <h4>TITOLO ORIGINALE : {{original_title}}</h4>
   <span>LINGUA ORIGINALE: </span><img :src=flagSource alt="niente">
   <h6>VOTO MEDIO :{{vote}}</h6>
    
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    title: String ,
    original_title: String,
    original_language: String,
    vote: Number
  },

  data(){
    return{
      flagSource : ''
    }
  },

  mounted(){
    this.sourceGenerator(this.original_language)
  },

  methods : {
    sourceGenerator(lang){
      if (lang == 'it'){
        this.flagSource = 'https://upload.wikimedia.org/wikipedia/commons/thumb/0/03/Flag_of_Italy.svg/1500px-Flag_of_Italy.svg.png'
      } else if (lang == 'en'){
        this.flagSource ='https://upload.wikimedia.org/wikipedia/commons/thumb/a/ae/Flag_of_the_United_Kingdom.svg/640px-Flag_of_the_United_Kingdom.svg.png'
      }else{
        this.flagSource = 'https://upload.wikimedia.org/wikipedia/commons/thumb/0/04/Nuvola_unknown_flag.svg/1200px-Nuvola_unknown_flag.svg.png'
      }
    }

  }


}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

.card{
  max-width: 500px;
  margin-bottom:20px;
  background-color:rgb(186, 240, 222);

  img{
    width: 50px;
  }
}

</style>
