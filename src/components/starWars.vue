<template>
  <div>
    <h1>Star Wars Planets</h1>
    <div class="planets" v-for="planet of planets">
      <h2>{{ planet.name }}</h2>
      <p>{{ planet.climate }}</p>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      planets: [],
    };
  },
  created() {
    this.$http.get("https://swapi.dev/api/planets").then((data) => {
      console.log(data);
      this.planets = data.body.results;
    });
  },
};
</script>