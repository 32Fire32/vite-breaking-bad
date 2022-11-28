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
      filterCharacters: [],
      cat: "Select Category",
      hiding: true,
    };
  },
  // computed: {
  //   filter() {
  //     this.characters.forEach((element, i) => {
  //       if (this.cat === "Breaking Bad") {
  //         if (!element.category.includes("Breaking Bad")) {
  //           this.characters.splice(i, 1);
  //         }
  //       } else if (this.cat === "Better Call Saul") {
  //         if (!element.category.includes("Better Call Saul")) {
  //           this.characters.splice(i, 1);
  //         }
  //       } else if (this.cat === "Select Category") {
  //         if (element.category.includes("Select Category")) {
  //           this.characters.splice(i, 1);
  //         }
  //       }
  //     });
  //   },
  // },
  methods: {},

  created() {
    this.hiding = false;
    axios
      .get("https://www.breakingbadapi.com/api/characters")
      .then((response) => {
        // console.log(response.data);
        this.characters = response.data;
        this.hiding = true;
      });
  },
  updated() {
    if (this.cat === "Select Category") {
      axios
        .get("https://www.breakingbadapi.com/api/characters")
        .then((response) => {
          this.characters = response.data;
        });
    }
    this.characters.forEach((element, i) => {
      if (this.cat === "Breaking Bad") {
        if (!element.category.includes("Breaking Bad")) {
          this.characters.splice(i, 1);
          this.filterCharacters.push(i);
        }
      } else if (this.cat === "Better Call Saul") {
        if (!element.category.includes("Better Call Saul")) {
          this.characters.splice(i, 1);
          this.filterCharacters.push(i);
        }
      }
    });
  },
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
      <AppCharacterCard
        v-for="(character, index) in characters"
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
