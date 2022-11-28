<script>
export default {
  name: "AppHeader",
};
</script>

<template>
  <header class="d-flex align-items-center">
    <div class="me-3">
      <img src="../assets/logo (1).png" alt="bb" />
    </div>
    <div class="title">Breaking Bad Api</div>
  </header>
</template>

<style scoped lang="scss">
header {
  padding: 20px;
}
img {
  height: 35px;
}

.title {
  color: var(--secondary-color);
  font-weight: bold;
  font-size: 1.3rem;
}
</style>
