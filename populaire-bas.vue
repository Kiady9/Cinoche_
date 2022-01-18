<template>
  <div class="container">
    <NuxtLogo />
    <h1>Random Cocktail</h1>
    <ul>
      <li v-for="drink in drinks" :key="drink.idDrink">
        <p>{{ drink[0]["strDrink"] }}</p>
        <!-- <img :src="drink[0]['strDrinkThumb']" /> -->
        <p>{{ drink[0]["strInstructions"] }}</p>
      </li>
    </ul>
    <h1>Bonjouuuur</h1>

    <hr />
    <cp />
    <modal />
    <NuxtLink to="/">Home</NuxtLink>
  </div>
</template>
<script>
export default {
  async asyncData({ $http }) {
    const drinks = await $http.$get(
      "https://www.thecocktaildb.com/api/json/v1/1/random.php"
    );
    return { drinks };
  },
};
</script>
<style scoped>
.container {
  background-color: rgb(255, 255, 255);
  border: blueviolet;
}
</style>