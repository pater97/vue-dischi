<template>
<!-- contenitore principale -->
    <div class="main_container">
      <!-- selettore di genere -->
      <div class="select_kind">
        <select v-model="selected" @change="filteredKind" id="kind_select">
          <option value="all">
            all
          </option>
          <option value="Rock">
            Rock
          </option>
          <option value="Pop">
              Pop
          </option>
          <option value="Jazz">
              Jazz
          </option>
          <option value="Metal">
              Metal
          </option>
        </select>
    </div>
      <!-- condizione positiva -->
      <section class="row" v-if="!loading">
         <card
        v-for="card in filteredKind"
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
        card,
    },
    // oggetti
    data(){
      return {
        cards:[],
        loading:true,
        selected:""
      }
    },
    methods:{
      
    },
    computed:{
      filteredKind(){
        if(this.selected == "all"){
          return this.cards
        }else{
          const filteredcard = this.cards.filter(card =>{
            return card.genre.includes(this.selected)
          })
          return filteredcard
        }
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