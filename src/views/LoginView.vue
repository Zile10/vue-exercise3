<template>
  <div class="login">
    <Login @login="$emit('login')"/>
  </div>
</template>

<script>
import Login from '../components/Login.vue'
export default {
  components: {
    Login
  },
  methods: {
    
  },
}
</script>

<style>
.login{
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>