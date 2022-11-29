<script>
import { store } from "../store.js";

export default {
  name: "AppFound",
  props: {
    info: Object,
  },
  data() {
    return {
      store,
    };
  },
  methods: {
    isLong() {
      return this.store.characters.length;
    },
  },
};
</script>

<template>
  <div class="found">
    <span>Found {{ isLong() }} characters</span>
  </div>
</template>

<style scoped lang="scss">
.found {
  padding: 10px 30px;
  color: #fff;
  background-color: #10161d;
}
</style>
