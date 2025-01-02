<template>
  <nav id="header">
    <RecipesRecherche class="app" @handleRecherche="searchRecipes" id="recherche" />
  </nav>
</template>

<script >
import RecipesRecherche from "./RecipesRecherche.vue";
export default {
  components: {
    RecipesRecherche,
  },
  methods: {
    searchRecipes(meal, diet, cuisineTypeSelected, mealTypeSelected) {
      this.$emit(
        "handleRecherche",
        meal,
        diet,
        cuisineTypeSelected,
        mealTypeSelected
      );
      console.log(this.meal)
    },
  },
};
</script>

<style scoped>
#header {
  flex-direction: row;
  display: inline-flex;
  position: fixed;
  background: #e5ba73;
  color: #e6e5a3;
  top: 0;
  left: 0;
  height: 120px;
  width: 100%;
  align-items: center;
  margin-right: 50px;
  justify-content: space-between;
  -webkit-justify-content: space-between;
}
#header a {
  padding: 20px;
  font-weight: bold;
  color: black;
  padding: 10px;
  justify-content: center;
  display: flex;
  white-space: nowrap;
  align-items: center;
  transition: color 2s;
}
.header {
  position: fixed; /* or sticky */
  top: 0;
  background-color: powderblue;
  height: 120px;
  width: 100%;
  padding: 16px;
  display: flex;
  align-items: flex-end;
  border-bottom-left-radius: 8px;
  border-bottom-right-radius: 8px;
}
.app {
  border: black dashed 1px;
  display: flex;
  align-items: flex-end;
}
</style>