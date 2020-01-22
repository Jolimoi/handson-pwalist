<template>
  <div class="login">
    <h3>Sign In</h3>
    <input type="text" v-model="email" placeholder="Email" />
    <br />
    <input type="password" v-model="password" placeholder="Password" />
    <br />
    <button @click="login">Connection</button>
    <p>
      Pas de compte ?
      <router-link to="/register">Inscription</router-link>
    </p>
  </div>
</template>

<script>
import firebase from "firebase";

export default {
  name: "Login",
  data() {
    return {
      email: "",
      password: ""
    };
  },

  methods: {
    login() {
      // Exercice 2.2
    }
  }
};
</script>

<style scoped>
</style>
