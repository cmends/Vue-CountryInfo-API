<template>
  <div class="wrapper">
    <!-- <p>{{ "this is my single view page" }}</p> -->
    <button class="search-btn" @click="$router.go(-1)">BACK</button>
    <div class="content">
      <div class="images">
        <img :src="singleCountry.flags?.png" alt="" />
      </div>
      <div class="info">
        <p>Name : {{ singleCountry.name?.common }}</p>
        <p>Region : {{ singleCountry.region }}</p>
        <p>Capital:{{singleCountry.capital[0]}}</p>
        <p>Sub-Region:{{singleCountry.subregion}}</p>
        <p>Population:{{singleCountry.population}}</p>
        <p>Languages:{{singleCountry.languages}}</p>
        <p>Currency:{{singleCountry.currency}}</p>
      </div>
    </div>
  </div>
</template>
<script>
import { mapActions, mapGetters } from "vuex";
export default {
  name: "SinglePage",
  data: () => ({}),
  created() {
    const countryName = this.$route.params.name;
    this.getSingleCountry(countryName);
  },
  computed: {
    ...mapGetters({
      singleCountry: "getSingleCountry",
    }),
  },
  methods: {
    ...mapActions({
      getSingleCountry: "getSingleCountry",
    }),
  },
};
</script>
<style lang="scss" scoped>

.search-btn{
  background-color: azure;
  padding: 10px 20px;
    margin-left: 20px;
    border-radius: 4px;
}
.content {
  display: flex;
  justify-content: space-between;
}
button {
  cursor: pointer;
}
.info{
  align-items: center;
  margin: auto;
}
.images{
  width:400px;
  height: 200px;
  margin: auto;
  align-items: center;
}
</style>