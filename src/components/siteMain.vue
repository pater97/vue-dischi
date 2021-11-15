<template>
<!-- contenitore principale -->
    <div class="main_container">
      <!-- condizione positiva -->
      <section class="row" v-if="!loading">
         <card
        v-for="card in cards"
        :key="card.id"
        :image="card.poster"
        :title="card.title"
        :artist="card.author"
        :year="card.year"
        />
      </section>
      <!-- condizione negativa -->
      <section class="loading" v-else>
        <h1>
          loading...
        </h1>
      </section>
    </div>
</template>

<script>
// importazioni 
import card from './card.vue'
import axios from 'axios'
export default {
    components:{
        card
    },
    // oggetti
    data(){
      return {
        cards:[],
        loading:true
      }
    },
    // richiamo api 
     mounted(){
    axios
    .get('https://flynn.boolean.careers/exercises/api/array/music')
    .then(r =>{
      this.cards = r.data.response;
      this.loading = false
    }).catch(e=>{
      console.log(e,'ops!');
    })
  }
}
</script>

<style lang="scss">
.main_container{
  width: 97%;
  margin: auto;
}
  .row{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }
  .loading{
    display: flex;
    justify-content: center;
    align-items: center;
    color: white;
    transform: scale(200%);
    transition: all 1s;
  }
</style>