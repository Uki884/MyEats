<template>
  <div
    id="target-logo"
    class="generate-content"
  >
    <div class="generate-content__item">
      <div class="generate-content__item--right">{{text}}</div>
      <div class="generate-content__item--left">Eats</div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    text: {
      type: String,
      default: 'Uber'
    }
  }
}
</script>

<style lang="scss" scoped>
@import url('https://db.onlinewebfonts.com/c/28163c87a18792d6798c430b4e3e5cbf?family=Uber+Move');
.generate-content {
  width: 100%;
  margin-top: 24px;
  height: 300px;
  background: black;
  &__item {
    font-family: 'Uber Move';
    display: flex;
    height: 100%;
    font-size: 140px;
    justify-content: center;
    align-items: center;
    @media screen and (max-width: 480px) {
      font-size: 62px !important;
    }
    &--right {
      color: white;
    }
    &--left {
      color: #3fc167;
    }
  }
}
</style>
