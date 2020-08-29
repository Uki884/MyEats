<template>
  <InputsField
    v-model="inputValue"
    @click="$emit('click')"
  />
</template>

<script>
import InputsField from '@/components/Molecules/InputsFIeld.vue'
export default {
  components: {
    InputsField
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

<style></style>
