<template>
  <NavBar/>
  <router-view/>
  <Footer/>
</template>

<script>
import NavBar from "./components/NavBar.vue"
import Footer from "./components/Footer.vue"

export default {
  components: {
    NavBar,
    Footer
  }
}
</script>

<style lang="scss">
html {
  font-size: 62.5%;
}

body {
  height: 100vh!important;
  
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
}

</style>
