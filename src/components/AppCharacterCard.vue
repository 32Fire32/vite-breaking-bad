<script>
export default {
  name: "AppCharactersCard",
};
</script>

<template>
  <div class="text-center">
    <img class="img-fluid" src="" alt="" />
    <h3>CardTitle</h3>
    <div class="category">
      <span>Category</span>
    </div>
    <div class="status">
      <small>Status</small>
    </div>
  </div>
</template>

<style scoped lang="scss">
.text-center {
  height: 300px;
  width: 300px;
  border: 1px solid red;
}

h3 {
  color: var(--secondary-color);
}

span,
small {
  color: gray;
}
</style>
