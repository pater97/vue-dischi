<template>
  <div id="app">
    <siteHeader />
    <siteMain class="main"/>
  </div>
</template>

<script>
import siteHeader from "./components/siteHeader.vue";
import siteMain from "./components/siteMain.vue";
export default {
  name: "App",
  components: {
    siteHeader,
    siteMain,
  },
};
</script>

<style lang="scss">
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: "Montserrat";
  background-color:#1E2D3B ;
  .main{
    padding: 2rem 0 8rem 0;
  } 
}
</style>
