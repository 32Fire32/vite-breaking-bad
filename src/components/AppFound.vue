<script>
export default {
  name: "AppFound",
  props: {
    info: Object,
  },
  methods: {
    isLong() {
      return this.info.length;
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
