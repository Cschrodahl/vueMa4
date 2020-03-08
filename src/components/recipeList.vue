<template>
  <div id="app">
    <div v-for="recipe in recipes" v-bind:key="recipe.id">
      <recipe
        v-bind:thumbnail="recipe.thumbnail"
        v-bind:title="recipe.title"
        v-bind:ingredients="recipe.ingredients"
        v-bind:website="recipe.href"
      ></recipe>
    </div>
  </div>
</template>

<script>
import recipe from "./recipe.vue";

export default {
  name: "recipeList",
  components: {
    recipe
  },
  data() {
    return {
      recipes: []
    };
  },
  mounted() {
    fetch("https://cors-anywhere.herokuapp.com/http://www.recipepuppy.com/api")
      .then(response => {
        return response.json();
      })
      .then(result => {
        this.recipes = result.results;
      });
  }
};
</script>