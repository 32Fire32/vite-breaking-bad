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
        console.log(response.data);
        this.characters = response.data;
      });
  },
};
</script>

<template>
  <section class="container p-5">
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
