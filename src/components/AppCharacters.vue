<script>
import axios from "axios";
import AppCharacterCard from "./AppCharacterCard.vue";
import AppFound from "./AppFound.vue";
export default {
  name: "AppCharacters",
  components: {
    AppCharacterCard,
    AppFound,
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
        console.log(response.data.length);
        this.characters = response.data;
      });
  },
};
</script>

<template>
  <section class="container p-5 my-3">
    <AppFound :info="characters" />
    <div class="row">
      <AppCharacterCard v-for="character in characters" :info="character" />
    </div>
  </section>
</template>

<style scoped lang="scss">
.container {
  background-color: var(--secondary-color);
}
</style>
