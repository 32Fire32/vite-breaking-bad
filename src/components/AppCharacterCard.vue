<script>
export default {
  name: "AppCharactersCard",
  props: {
    info: Object,
  },
};
</script>

<template>
  <div class="text-center">
    <img class="img-fluid" :src="info.img" :alt="info.name" />
    <h3>{{ info.name }}</h3>
    <div class="category">
      <span>{{ info.category }}</span>
    </div>
    <div class="status">
      <small>{{ info.status }}</small>
    </div>
  </div>
</template>

<style scoped lang="scss">
.text-center {
  height: 300px;
  width: 300px;
  background-color: var(--primary-color);
}

h3 {
  color: var(--secondary-color);
}

span,
small {
  color: gray;
}
</style>
