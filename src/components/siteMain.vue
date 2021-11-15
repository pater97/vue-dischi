<template>
    <div class="main_container">
        <card/>
    </div>
</template>

<script>
import card from './card.vue'
import Axios from 'Axios'
export default {
    components:{
        card
    },
     mounted(){
    Axios
    .get('https://flynn.boolean.careers/exercises/api/array/music')
    .then(r =>{
      console.log(r);
    }).catch(e=>{
      console.log(e,'ops!');
    })
  }
}
</script>

<style lang="scss">

</style>