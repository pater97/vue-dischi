<template>
    <div class="main_container">
      <section class="row">
         <card
        v-for="card in cards"
        :key="card.id"
        :image="card.poster"
        :title="card.title"
        :artist="card.author"
        :year="card.year"
        />
      </section>
    </div>
</template>

<script>
import card from './card.vue'
import axios from 'axios'
export default {
    components:{
        card
    },
    data(){
      return {
        cards:[]
      }
    },
     mounted(){
    axios
    .get('https://flynn.boolean.careers/exercises/api/array/music')
    .then(r =>{
      this.cards = r.data.response;
      console.log(this.cards);
    }).catch(e=>{
      console.log(e,'ops!');
    })
  }
}
</script>

<style lang="scss">
.main_container{
  width: 90%;
  margin: auto;
}
  .row{
    display: flex;
    flex-wrap: wrap;
  }
</style>