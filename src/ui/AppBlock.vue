<template>
  <div class="card">
    <h3>Title card</h3>
    <slot name="header"/>
    <slot name="default">
      No Text
    </slot>
    <div v-if="this.$slots.footer">
      <slot name="footer"/>
    </div>
  </div>
</template>
<script>
export default {
  name: 'AppBlock',
  mounted() {
    console.log('-=-=-=', this.$slots);
  },
};
</script>
<style lang="scss">
</style>
