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
    <div class="image">
      <img :src="info.img" :alt="info.name" />
    </div>

    <div class="infoCharacters">
      <div class="name">
        <h5>{{ info.name }}</h5>
      </div>
      <div class="category">
        <span>{{ info.category }}</span>
      </div>
      <div class="status">
        <small>{{ info.status }}</small>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.text-center {
  width: calc(100% / 6);
  margin: 20px;
  padding: 10px;
  background-color: var(--primary-color);

  h5 {
    color: var(--secondary-color);
  }

  span,
  small {
    color: gray;
  }

  img {
    width: 100%;
    max-height: 70%;
    object-fit: cover;
    object-position: top;
  }

  .infoCharacters {
    max-height: 30%;
  }
}
</style>
