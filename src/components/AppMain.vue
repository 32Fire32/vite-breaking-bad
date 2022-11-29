<script>
import axios from "axios";
import { store } from "../store.js";

import AppCharacters from "./AppCharacters.vue";
import AppForm from "./AppForm.vue";
export default {
  name: "AppMain",
  components: {
    AppCharacters,
    AppForm,
  },
  data() {
    return {
      store,
    };
  },
  methods: {
    apiChar() {
      axios
        .get("https://www.breakingbadapi.com/api/characters", {
          params: {
            category: this.store.cat,
            // status: this.store.status,
          },
        })
        .then((resp) => {
          this.store.characters = resp.data;
          store.hiding = true;
        });
    },
  },
  created() {
    this.apiChar();
  },
};
</script>

<template>
  <main class="container mt-5">
    <AppForm @search="apiChar" />
    <AppCharacters />
  </main>
</template>

<style scoped lang="scss"></style>
