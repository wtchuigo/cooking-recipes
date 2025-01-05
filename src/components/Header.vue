<template>
  <nav id="header">
    <RecipesRecherche
      @handleRecherche="searchRecipes"
      id="recherche"
    />
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

#recherche {
  padding: 20px;
  font-weight: bold;
  color: #2d2d2d;
  height: 70px;
  align-items: center;
  display: flex;
  margin-left: auto;
}
</style>