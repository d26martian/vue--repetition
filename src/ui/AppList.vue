<template>
  <div class="card mt-3">
    <ul>
      <li v-for="(item, idx) in 5" :key="idx">
        <slot :itemSlot="item" :idxSlot="idx" />
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'AppList',
};
</script>
<style lang="scss">
</style>
