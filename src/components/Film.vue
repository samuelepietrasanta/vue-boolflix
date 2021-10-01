<template>
  <div class="card">

   <h4>TITOLO : {{title}}</h4>
   <h4>TITOLO ORIGINALE : {{original_title}}</h4>
   <h6>LINGUA ORIGINALE : {{original_language}}</h6>
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
    vote: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

.card{
  max-width: 500px;
  margin-bottom:20px;
  background-color:rgb(186, 240, 222);
}

</style>
