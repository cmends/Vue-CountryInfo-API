<template>
  <div class="home">
    <input type="text" placeholder="Search for a country..." v-model="searchTerm" />
    <select class="filterr" name="" id="" v-model="selectTerm">
      <option value="">Filter by Region</option>
      <option :value="region" v-for="region in regions" :key="region">
        {{ region }}
      </option>
    </select>
    <div class="home_content">
      <Card :countries="filteredCountries"> </Card>
    </div>
  </div>
</template>

<script>
import { mapActions, mapGetters } from "vuex";
import Card from "@/components/Card.vue";
export default {
  name: "HomeView",
  components: {
    Card,
  },
  data: () => ({
    username: "",
    searchTerm: "",
    regions: [],
    selectTerm: ""
  }),
  async mounted() {
    await this.getAllCountries();
    console.log(this.countries);
    await this.getRegions();
  },
  computed: {
    ...mapGetters({
      countries: "getCountries",
    }),
    filteredCountries() {
      if (this.searchTerm) {
        return this.countries.filter((country) =>
          country.name.common
            .toLowerCase()
            .includes(this.searchTerm.toLowerCase())
        );
      } else if (this.selectTerm) {
        return this.countries.filter(
          (country) => country.region === this.selectTerm
        );
      }
      else {
        return this.countries;
      }
    },
  },
  methods: {
    ...mapActions({
      getAllCountries: "getAllCountries",
    }),
    getRegions() {
      let regionsMap = this.countries.map((country) => country.region);
      console.log(regionsMap);
      const setRegions = [...new Set(regionsMap)];
      console.log(setRegions);
      this.regions = setRegions;
    },
  },
};
</script>

<style lang="scss" scoped>

.filterr{
  padding: 10px 20px;
    background-color: azure;
    border-radius: 4px;
}
// .home {
//   // &_content {
//   //   // border: 1px solid red;
//   //   // border-radius: 4px;
//   // }
// }

input {
  padding: 10px 20px;
  margin-left: 20px;
  background-color: white;
  border-radius: 4px;
}
</style>