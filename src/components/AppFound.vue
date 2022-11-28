<script>
export default {
  name: "AppFound",
  props: {
    info: Object,
  },
};
</script>

<template>
  <div class="found">
    <p>Found {{ info.length }} characters</p>
  </div>
</template>

<style scoped lang="scss">
.found {
  padding: 10px;
  color: #fff;
  background-color: #10161d;
}
</style>
