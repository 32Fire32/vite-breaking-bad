<script>
import { store } from "../store.js";

import AppCharacterCard from "./AppCharacterCard.vue";
import AppFound from "./AppFound.vue";
import AppLoading from "./AppLoading.vue";
export default {
  name: "AppCharacters",
  components: {
    AppCharacterCard,
    AppFound,
    AppLoading,
  },

  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <AppLoading :class="{ hide: store.hiding }" />
  <section class="container p-5 my-3" :class="{ hide: !store.hiding }">
    <AppFound :info="store.characters" />
    <div class="row justify-content-between">
      <AppCharacterCard
        v-for="(character, index) in store.characters"
        :name="character.name"
        :img="character.img"
        :category="character.category"
        :status="character.status"
      />
    </div>
  </section>
</template>

<style scoped lang="scss">
.container {
  background-color: var(--secondary-color);
}
.hide {
  display: none;
}
</style>
