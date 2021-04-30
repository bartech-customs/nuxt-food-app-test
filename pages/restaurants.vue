<template>
  <main class="container restaurant">
    <div class="restaurantheading">
      <h1>Restaurants</h1>
      <AppSelect
        @change="selectedRestaurant = $event"
        :selectoptions="restaurantOptions"
      />
    </div>
    <AppRestaurantInfo :datasource="filteredRestaurants" />
  </main>
</template>

<script>
import { mapState } from "vuex";

export default {
  data() {
    return {
      selectedRestaurant: "",
      restaurantOptions: ["tacos", "pizza", "dim sum"]
    };
  },
  computed: {
    ...mapState(["fooddata"]),
    filteredRestaurants() {
      if (this.selectedRestaurant) {
        return this.fooddata.filter(el => {
          let name = el.name.toLowerCase();
          return name.includes(this.selectedRestaurant);
        });
      }
      return this.fooddata;
    }
  }
};
</script>

<style lang="scss" scoped></style>
