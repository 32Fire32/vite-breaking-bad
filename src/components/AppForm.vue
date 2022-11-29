<script>
import { store } from "../store.js";

export default {
  name: "AppForm",
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <form>
    <div>
      <select
        class="form-select w-auto"
        id="floatingSelect"
        aria-label="Floating label select example"
        v-model="store.cat"
        @click="$emit('search')"
      >
        <option value="" selected>Select Category</option>
        <option value="Breaking Bad">Breaking Bad</option>
        <option value="Better Call Saul">Better Call Saul</option>
      </select>
    </div>
  </form>
</template>

<style scoped lang="scss"></style>
