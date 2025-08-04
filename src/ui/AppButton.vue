<template>
  <button class="btn" :class="color" @click="$emit('action')">
    <slot/>
  </button>
</template>
<script>
export default {
  name: 'AppButton',
  emits: ['action'],
  props: {
    color: {
      type: String,
      default: '',
      validator(value) {
        return ['', 'btn-primary', 'btn-danger'].includes(value);
      },
    },
  },
};
</script>
<style lang="scss">
</style>
