<template>
  <div class="cards-section">
    <div class="card" v-for="country in countries" :key="country.name.common" @click="
      this.$router.push({
        name: 'SingleCountry',
        params: { name: country.name.common },
      })
    ">
      <img :src="country.flags.png" alt="" />
      <p>{{ country.name.common }}</p>
      <p class="card-text-capital" v-if="country.capital">
        Capital:
        <span v-for="(capital, index) in country.capital" :key="index">{{
            capital
        }}</span>
      </p>
      <p>{{ country.population }}</p>
      <p>{{ country.region }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    countries: {
      type: Array,
    },
  },
};
</script>

<style scoped lang="scss">
.cards-section {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: space-evenly;
  padding-top: 50px;
}

.card {
  background-color: beige;
  border: 1px solid black;
  box-shadow: 20px 20px 100px 10px gainsboro;
  border-radius: 10px;
  margin-bottom: 10px;
  cursor: pointer;
}

img {
  width: 280px;
  height: 150px;
  border-radius: 10px;
}

p {
  padding-left: 5px;
  font-family:'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
  font-size: 18px;
  font-weight: bold;
}
</style>
