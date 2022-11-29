<script>
export default {
  name: "AppLoading",
};
</script>

<template>
  <div class="row">
    <div class="col-xs-12">
      <h3>LOADING...</h3>
    </div>
    <div class="col-xs-12 mt-5">
      <i class="ex-11-icon fas fa-circle-notch"></i>
    </div>
  </div>
</template>

<style scoped lang="scss">
.row {
  color: var(--secondary-color);
  font-size: 2rem;
  text-align: center;
  .ex-11-icon {
    animation-name: spin-inverse;
    animation-duration: 1s;
    animation-timing-function: linear;
    animation-iteration-count: infinite;
  }
}
@keyframes spin-inverse {
  0% {
    transform: rotate(0deg);
  }
  25% {
    transform: rotate(90deg);
  }
  50% {
    transform: rotate(180deg);
  }
  75% {
    transform: rotate(270deg);
  }
  100% {
    transform: rotate(0deg);
  }
}
</style>
