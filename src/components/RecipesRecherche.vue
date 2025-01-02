<template>
  <form
    id="recherche"
    @submit.prevent="
      $emit(
        'handleRecherche',
        meal,
        diet,
        cuisineTypeSelected,
        mealTypeSelected
      )
    "
  >
    <div>
      <input type="text" placeholder="Meal.." v-model="meal" />
    </div>
    <div>
      <select v-model="diet" >
        <option disabled value="">Please select one</option>
        <option>balanced</option>
        <option>high-fiber</option>
        <option>high-protein</option>
        <option>low-carb</option>
        <option>low-fat</option>
        <option>low-sodium</option>
      </select>
    </div>
    <div>
      <select v-model="cuisineTypeSelected" >
        <option disabled value="">Please select one</option>
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
      <select v-model="mealTypeSelected" >
        <option disabled value="">Please select one</option>
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
          class="searchStock"
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
        }
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
  color: black;
}
#recherche {
  border: black dashed 1px;
  display: flex;
  align-items: flex-end;
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