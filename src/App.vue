<template>
  <!-- <div v-if="isAuthenticated"> -->
    <NavBar/>
    <router-view/>
    <Footer/>
  <!-- </div> -->
  <!-- <LoginView v-else  @login="authenticate()"/> -->
</template>

<script>
  import LoginView from '@/views/LoginView.vue';
  import NavBar from '@/components/NavBar.vue';
  import Footer from '@/components/Footer.vue';
  export default {
    components: {
      LoginView,
      NavBar,
      Footer
    },
    data() {
      return {
        isAuthenticated: false,
      }
    },
    methods: {
      authenticate(){
        this.isAuthenticated = true
        console.log('authenticated');
      }
    }
  }
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
  color: #fff;

}

nav a {
  font-weight: bold;
  text-decoration: none;
  color: #fff;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>