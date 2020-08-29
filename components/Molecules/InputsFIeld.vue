<template>
  <div class="inputs-field">
    <div class="inputs-field__input">
      <div class="inputs-field__input--item">
        <BaseTextField
          v-model="inputValue"
          class="text"
        />
      </div>
      <div class="inputs-field__input--item">
        <div class="flex">
          <BaseButton
            class="button"
            label="ダウンロード"
            width="120"
            @click.native="$emit('click')"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BaseButton from '@/components/Atoms/Button/BaseButton.vue'
import BaseTextField from '@/components/Atoms/Input/BaseTextField.vue'
export default {
  components: {
    BaseTextField,
    BaseButton
  },
  props: {
    value: {
      type: String,
      default: ''
    }
  },
  computed: {
    inputValue: {
      get() {
        return this.value
      },
      set(val) {
        this.$emit('input', val)
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.inputs-field {
  &__input {
    display: flex;
    justify-content: center;
    margin-bottom: 12px;
    &--item {
      &:first-child {
        margin-right: 24px;
      }
    }
  }
  &__buttons {
    width: 300px;
    margin: 0 auto;
  }
}
</style>
