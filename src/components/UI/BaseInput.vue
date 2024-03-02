<template>
  <input :value="modelValue" @input="updateInput" class="base-input" />
</template>

<script>
export default {
  props: {
    modelValue: [String, Number],
  },
  methods: {
    updateInput(event) {
      this.$emit('update:modelValue', event.target.value);
    },
  },
  name: 'base-input',
};
</script>

<style scoped>
.base-input {
  height: 48px;
  border: 1px solid #000;
  border-radius: 8px;
  font-size: 16px;
  padding: 0 10px;
}
</style>
