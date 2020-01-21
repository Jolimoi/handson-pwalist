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

export default {
  name: "Form",
  data() {
    return {
      ingredient: "",
      docs: []
    }
  },
  mounted() {
    // Exercice 1.2
  },
  methods: {
    onSubmit: function() {
      // Exercice 1.1
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
