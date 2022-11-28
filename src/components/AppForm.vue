<script>
export default {
  name: "AppForm",
  props: {
    info: Object,
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
        v-model="category"
        ;
      >
        <option selected>Select Category</option>
        <option value="1">Breaking Bad</option>
        <option value="2">Better Call Saul</option>
      </select>
    </div>
  </form>
</template>

<style scoped lang="scss">
form {
  position: absolute;
  top: -50px;
  left: 0;
}
</style>
