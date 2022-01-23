<template>
  <div class="wrapper">
    <div class="items">
      <MainItem
          v-for="user of users"
          v-bind:user="user"
      />
      <BeerItem
          v-for="beer of beers"
          v-bind:beer="beer"
          v-on:newBeer="newBeer"
      />
    </div>
  </div>
</template>

<script>
import MainItem from "./MainItem";
import BeerItem from "./BeerItem";
export default {
  props: ["users", "beers"],
  name: "Main",
  components: {
    MainItem,
    BeerItem
  },
  methods: {
    newBeer(id){
      this.$emit('newBeer', id)
    }
  }
}
</script>

<style scoped>
  .wrapper {
    padding: 0 20px;
    max-width: 1200px;
    width: 100%;
    height: 100%;
    margin: 0 auto;
  }
  .items {
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-direction: row;
  }
  @media (max-width: 960px) {
    .items {
      display: flex;
      flex-direction: column;
    }
  }
</style>