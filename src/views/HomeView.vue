<template>
  <Header @handleRecherche="searchRecipes" />
  <div id="body">
    <RecipeItem
      :image="recipe.recipe.image"
      :label="recipe.recipe.label"
      :attributes="recipe.recipe.dietLabels.join(', ')"
      :url="recipe.recipe.url"
      v-for="recipe in recipes"
    />
  </div>
  <Footer />
</template>

<script>
import RecipeItem from "../components/RecipeItem.vue";
import Footer from "@/components/Footer.vue";
import Header from "../components/Header.vue";
export default {
  name: "HomeView",
  components: {
    RecipeItem,
    Header,
    Footer,
  },
  data() {
    return {
      meal: "",
      diet: "",
      cuisineTypeSelected: "",
      mealTypeSelected: "",
      recipes: [],
    };
  },
  methods: {
    async searchRecipes(mealval, dietval, cuisineTypeSelectedval, mealTypeSelectedval) {
      this.meal = mealval;
      this.diet = dietval;
      this.cuisineTypeSelected = cuisineTypeSelectedval;
      this.mealTypeSelected = mealTypeSelectedval;
      const appId = "0b3cb4ec";
      const appKey = "05e1aae0523be8829b56bd85ff46c619";
      const url = `https://api.edamam.com/api/recipes/v2?type=public&q=${this.meal}&app_id=${appId}&app_key=${appKey}&diet=${this.diet}&cuisineType=${this.cuisineTypeSelected}&mealType=${this.mealTypeSelected}`;
      let resp = await fetch(url, {
        headers: {
          accept: "application/json",
          "Edamam-Account-User": "wtchuigo",
          "Accept-Language": "en",
        },
      });
      this.recipes = (await resp.json()).hits;
      console.log(this.meal)
      console.log(this.recipes);
    },
  },
  watch: {
    handleRecherche: function () {
      this.searchRecipes();
    },
  },
  mounted() {
    this.searchRecipes();
  },
};
</script>

<style scoped>
 #body{
    
    display: inline-block;
    margin-top: 7em;
    width: 100%;
    height: 100%;
    margin-bottom: 7.5em;
    min-height: 80%;
  }
  li {
    counter-increment: index; 
    display: flex;
    align-items: center;
    padding: 12px 0;
    box-sizing: border-box;
  }
  
</style>
