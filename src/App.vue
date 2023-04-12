<script>

import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import AppFooter from "./components/AppFooter.vue";


export default {

  data() {
    return {

    }
  },

  emits: [

  ],

  components: {
    AppHeader,
    AppMain,
    AppFooter,
  },


  computed: {
  },



}

</script>

<template>
  <div id="main-container">
    <div id="back-to-top-arrow">
      <i class="fa-solid fa-angle-up"></i>
    </div>
    <AppHeader></AppHeader>
  
    <AppMain></AppMain>
  
    <AppFooter></AppFooter>

  </div>
  

</template>

<style scoped>

#main-container {
  position: relative;

}

#back-to-top-arrow {
  position: fixed;
  bottom: -0.5%;
  right: 3%;
  z-index: 2;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 50px;
  height: 40px;
  border-radius: 5px;
  background-color: rgb(46, 46, 46);
  color: white;
}

</style>
