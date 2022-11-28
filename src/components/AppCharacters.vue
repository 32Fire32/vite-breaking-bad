<script>
import axios from "axios";
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
      characters: [],
      cat: "",
      hiding: true,
    };
  },
  created() {
    this.hiding = false;
    axios
      .get("https://www.breakingbadapi.com/api/characters")
      .then((response) => {
        console.log(response.data);
        this.characters = response.data;
        this.hiding = true;
      });
  },
  // updated() {
  //   if (this.cat === "Breaking Bad") {
  //     this.hiding = true;
  //     console.log(this.hiding);
  //     // console.log("la lunghezza dei characters è" + this.characters.length);
  //   }
  // },
};
</script>

<template>
  <AppLoading :class="{ hide: hiding }" />
  <section class="container p-5 my-3" :class="{ hide: !hiding }">
    <form>
      <div>
        <select
          class="form-select w-auto"
          id="floatingSelect"
          aria-label="Floating label select example"
          v-model="cat"
        >
          <option selected>Select Category</option>
          <option value="Breaking Bad">Breaking Bad</option>
          <option value="Better Call Saul">Better Call Saul</option>
        </select>
      </div>
    </form>
    <AppFound :info="characters" />
    <div class="row">
      <AppCharacterCard v-for="character in characters" :info="character" />
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
