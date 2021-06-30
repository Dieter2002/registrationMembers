<template>
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <div id="app">

      <!-- <Header /> -->

      <Dashboard v-bind:dashboard="dashboard" />


    
  </div>
</template>

<script>
// import Header from './components/Header.vue'
import Dashboard from "./components/Dashboard.vue";

export default {
  name: "app",
  components: {
    Dashboard,
    // Header
  },
  data() {
    return {
      dashboard: [
        {
          id: "TEST",
        },
        {
          id: "GEE",
        },
      ],
    };
  },
};
</script>

<style>
/* #app {

  
} */

body {
  /* background-color: #383740; */
}

</style>
