<script>
import AppCharacters from "./AppCharacters.vue";
export default {
  name: "AppMain",
  components: {
    AppCharacters,
  },
};
</script>

<template>
  <main class="container">
    <form>
      <div>
        <select
          class="form-select w-auto"
          id="floatingSelect"
          aria-label="Floating label select example"
        >
          <option selected>Select Category</option>
          <option value="1">Breaking Bad</option>
          <option value="2">Better Call Saul</option>
        </select>
      </div>
    </form>
    <AppCharacters />
  </main>
</template>

<style scoped lang="scss"></style>
