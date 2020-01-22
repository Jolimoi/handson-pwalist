<template>
  <div class="signup">
    <p>Créer son compte</p>
    <input type="text" v-model="email" placeholder="Email" />
    <br />
    <input type="password" v-model="password" placeholder="Password" />
    <br />
    <button @click="signUp">Valider</button>
    <p>
      <router-link to="/login">login</router-link>
    </p>
  </div>
</template>

 <script>
import firebase from "firebase";

export default {
  name: "Register",
  data() {
    return {
      email: "",
      password: ""
    };
  },
  methods: {
    signUp() {
      // Exercice 2.1
    }
  }
};
</script>

 <style scoped>
.signup {
  margin-top: 40px;
}
</style>
