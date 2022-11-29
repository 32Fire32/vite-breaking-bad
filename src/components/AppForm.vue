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
  <div class="d-flex">
    <form>
      <div>
        <select
          class="form-select w-auto"
          id="floatingSelect"
          aria-label="Floating label select example"
          v-model="store.cat"
          @change="$emit('search')"
        >
          <option value="" selected>Select Category</option>
          <option value="Breaking Bad">Breaking Bad</option>
          <option value="Better Call Saul">Better Call Saul</option>
        </select>
      </div>
    </form>
    <!-- <form class="ms-5">
      <div>
        <select
          class="form-select w-auto"
          id="floatingSelect"
          aria-label="Floating label select example"
          v-model="store.status"
          @click="$emit('search')"
        >
          <option value="" selected>Select Status</option>
          <option value="Alive">Alive</option>
          <option value="Deceased">Deceased</option>
          <option value="Presumed dead">Presumed dead</option>
        </select>
      </div>
    </form> -->
  </div>
</template>

<style scoped lang="scss"></style>
