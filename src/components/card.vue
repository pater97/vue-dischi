<template>
  <!-- colonna della card -->
  <div class="card_column">
      <!-- card -->
    <div class="card">
        <!-- immgaine  -->
      <img :src="image" alt="" />
      <!-- titolo -->
      <h2>
        {{ title.toUpperCase() }}
      </h2>
      <!-- artista -->
      <h5>
        {{ artist }}
      </h5>
      <!-- anno d'uscita  -->
      <h6>
        {{ year }}
      </h6>
    </div>
    <!-- /card -->
  </div>
  <!-- /colonna card -->
</template>

<script>
export default {
    // porps per la variabile da definire in seguito 
  props: {
    image: String,
    title: String,
    artist: String,
    year: String,
  },
};
</script>

<style lang="scss">
// misure colonna 
.card_column {
  width: calc((100% / 12) * 2);
  margin: 1rem 0;
//   impostazione card 
  .card {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    background-color: #2e3a46;
    margin: 1rem;
    padding: 1rem 0;
    height: 100%;
  }
  img,h2 {
    width: 80%;
  }
  h2 {
    font-size: 1.2rem;
    color: white;
    margin: 1rem 0;
  }
  h6{
      margin: 3px;
  }
  h6,h5{
      color: grey;
  }
}
</style>