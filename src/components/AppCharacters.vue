<script>
import axios from "axios";
import AppCharacterCard from "./AppCharacterCard.vue";
export default {
  name: "AppCharacters",
  components: {
    AppCharacterCard,
  },
  data() {
    return {
      characters: [],
    };
  },
  created() {
    axios
      .get("https://www.breakingbadapi.com/api/characters")
      .then((response) => {
        console.log(response);
        // this.characters = response.data.results;
      });
  },
};
</script>

<template>
  <section class="container">
    <div class="row">
      <AppCharacterCard class="col-sm-6 col lg-3" />
      <AppCharacterCard class="col-sm-6 col lg-3" />
      <AppCharacterCard class="col-sm-6 col lg-3" />
      <AppCharacterCard class="col-sm-6 col lg-3" />
    </div>
  </section>
</template>

<style scoped lang="scss"></style>
