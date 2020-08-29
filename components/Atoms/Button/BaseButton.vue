<template>
  <div class="button">
    <button
      :style="`background: ${color};width: ${width}px;`"
      type="button"
    >
      {{ label }}
    </button>
  </div>
</template>

<script>
export default {
  props: {
    label: {
      type: String,
      default: ''
    },
    color: {
      type: String,
      default: '#60B608'
    },
    width: {
      type: [String, Number],
      default: 90
    }
  }
}
</script>

<style lang="scss" scoped>
.button {
  width: 100%;
  &:first-child {
    margin-right: 24px;
  }
  button {
    cursor: pointer;
    border: none;
    outline: none;
    color: #fff;
    font-weight: bold;
    width: 100%;
    height: 36px;
  }
}

.cancel {
  background: #999999 !important;
}
</style>
