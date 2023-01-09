<template>
  <div>
    <form @submit.prevent="login" class="login-form">
      <label for="email" class="login-label">Email Address:</label>
      <input type="email" v-model="email" class="login-input" required/>
      <br/>
      <label for="password" class="login-label">Password:</label>
      <input type="password" v-model="password" class="login-input" required/>
      <br/>
      <button type="submit" class="login-button" @click="$emit('login')">Login</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: "",
      password: ""
    };
  },
  methods: {
    login() {
      console.log("Logging in with email: " + this.email + " and password: " + this.password);
    }
  }
};
</script>
<style>
.login-form {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.login-label {
  font-weight: bold;
  margin-bottom: 5px;
}

.login-input {
  width: 250px;
  height: 35px;
  font-size: 16px;
  margin-bottom: 10px;
  border: 1px solid #ccc;
  border-radius: 3px;
  padding: 0 10px;
}

.login-button {
  width: 100px;
  height: 35px;
  font-size: 16px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 3px;
  cursor: pointer;
}
</style>