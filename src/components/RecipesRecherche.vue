<template>
  <form id="recherche" @submit.prevent="submit">
    <div>
      <input type="text" placeholder="Meal.." v-model="meal" />
    </div>
    <div>
      <select v-model="diet">
        <option disabled value="">Diet...</option>
        <option>balanced</option>
        <option>high-fiber</option>
        <option>high-protein</option>
        <option>low-carb</option>
        <option>low-fat</option>
        <option>low-sodium</option>
      </select>
    </div>
    <div>
      <select v-model="cuisineTypeSelected">
        <option disabled value="">Cuisine Type...</option>
        <option>American</option>
        <option>Asian</option>
        <option>British</option>
        <option>Caribbean</option>
        <option>Chinese</option>
        <option>French</option>
        <option>Indian</option>
        <option>Italian</option>
        <option>Mexican</option>
        <option>Japanese</option>
      </select>
    </div>
    <div>
      <select v-model="mealTypeSelected">
        <option disabled value="">Meal type...</option>
        <option>Breakfast</option>
        <option>Dinner</option>
        <option>Lunch</option>
        <option>Snack</option>
        <option>Teatime</option>
      </select>
    </div>
    <div>
      <button id="submit" type="submit" value="Rechercher un livre">
        <img
          class="searchButton"
          src="../images/search_FILL0_wght400_GRAD0_opsz48.png"
        />
      </button>
    </div>
  </form>
</template>

<script>
export default {
  data() {
    return {
      meal: "",
      diet: "",
      cuisineTypeSelected: "",
      mealTypeSelected: "",
    };
  },
  methods: {
    submit: function () {
      if (this.meal == "") {
        alert("meal is empty");
      } else if (this.diet == "") {
        alert("select a diet");
      } else if (this.cuisineTypeSelected == "") {
        alert("select a cuisine type");
      } else if (this.mealTypeSelected == "") {
        alert("select a meal type");
      } else {
        this.$emit(
          "handleRecherche",
          this.meal,
          this.diet,
          this.cuisineTypeSelected,
          this.mealTypeSelected
        );
        this.meal = "";
        this.diet = "";
        this.mealTypeSelected = "";
        this.cuisineTypeSelected = "";
      }
    },
  },
};
</script>

<style>
#submit {
  vertical-align: middle;
  width: 45px;
  height: 45px;
  background: #faeab1;
  border: none;
  border-radius: 30px;
  color: #fff;
  font-size: 1.3em;
  outline: none;
  cursor: pointer;
  border: solid 1px black;
  box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
}

#recherche {
  border-radius: 7px;
  width: 100%;
  height: 120px;
  justify-content: center;
}

input[type="text"]::placeholder {
  color: rgba(0, 0, 0, 0.4);
    font-size: 12px;
}

#recherche div {
  padding: 5px;
  display: inline-block;
  align-items: flex-end;
  font-weight: bold;
}
#app div input {
  border-radius: 8px;
  padding: 5px;
  width: 90%;
  border: solid 1px black;
  background-color: #faeab1;
  height: 20px;
}
#recherche div select {
  border: solid black 1px;
  height: 30px;
  padding: 5px;
  border-radius: 8px;
  width: 100%;
  cursor: pointer;
  background-color: #faeab1;
  box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
}
</style>