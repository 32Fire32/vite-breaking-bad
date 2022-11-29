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
      hiding: true,
    };
  },
};
</script>

<template>
  <AppLoading :class="{ hide: hiding }" />
  <section class="container p-5 my-3" :class="{ hide: !hiding }">
    <AppFound :info="store.characters" />
    <div class="row">
      <AppCharacterCard
        v-for="(character, index) in store.characters"
        :info="character"
      />
    </div>
  </section>
</template>

<style scoped lang="scss">
.container {
  form {
    position: absolute;
    top: -50px;
    left: 0;
  }
  background-color: var(--secondary-color);
  position: relative;
}
.hide {
  display: none;
}
</style>
