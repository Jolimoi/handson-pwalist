<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <Form />
    <button @click="logout">Logout</button>
  </div>
</template>

<script>
// @ is an alias to /src
import Form from "@/components/Form.vue";
import firebase from 'firebase'

export default {
  name: "home",
  components: {
    Form
  },
  methods: {
    logout() {
      // Exercice 2.3
      firebase
        .auth()
        .signOut()
        .then(() => {
          this.$router.replace("login");
        });
    }
  }
};
</script>
