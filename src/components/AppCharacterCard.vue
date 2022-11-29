<script>
import { stringifyExpression } from "@vue/compiler-core";

export default {
  name: "AppCharactersCard",
  props: {
    name: String,
    category: String,
    status: String,
    img: {
      type: String,
      default: "https://via.placeholder.com/200x300",
    },
  },
};
</script>

<template>
  <div class="text-center">
    <div class="image">
      <img :src="img" :alt="name" />
    </div>

    <div class="infoCharacters">
      <div class="name">
        <h5>{{ name }}</h5>
      </div>
      <div class="category">
        <span>{{ category }}</span>
      </div>
      <div class="status">
        <small>{{ status }}</small>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.text-center {
  @include media-breakpoint-down(sm) {
    width: calc(100% / 2);
  }
  @include media-breakpoint-down(md) {
    width: calc(100% / 4);
  }
  @include media-breakpoint-down(sl) {
    width: calc(100% / 6);
  }
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
