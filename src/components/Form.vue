<template>
  <div class="hello">
    <div class="List">
      <form id="course" v-on:submit.prevent="onSubmit">
        <input type="text" v-model="ingredient" placeholder="ingredient" />
        <p>
          <input type="submit" value="Submit" />
        </p>
      </form>
      <div v-for="(doc) in docs" :key="doc.id">{{doc.name}}</div>
    </div>
  </div>
</template>

<script>
import firebase from "firebase";

let listeName

export default {
  name: "Form",
  data() {
    return {
      ingredient: "",
      docs: []
    };
  },
  mounted() {
    firebase.auth().onAuthStateChanged(user => {
      if (user) {
        // Exercice 2.4
        listeName = user.uid;
        firebase
          .firestore()
          .collection(listeName)
          .onSnapshot(querySnapshot => {
            querySnapshot.docChanges().forEach(change => {
              if (change.type === "added") {
                this.docs.push({
                  id: change.doc.id,
                  name: change.doc.data().name
                });
              }
            });
          });
      }
    });
  },
  methods: {
    onSubmit: function() {
      // Exercice 1.1
      firebase
        .firestore()
        .collection(listeName)
        .add({
          name: this.ingredient
        });
      // Exercice 2.4
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
