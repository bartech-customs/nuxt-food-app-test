<template>
  <main class="container">
    <AppHeader />
    <AppRestaurantInfo :datasource="fooddata" />
  </main>
</template>

<script>
export default {
  computed: {
    fooddata() {
      return this.$store.state.fooddata;
    }
  }
};
</script>

<style></style>
