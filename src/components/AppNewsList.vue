<template>
  <div>
    <hr/>
    <ul>
      <li v-for="item in news" :key="item.id">
        {{ item.title }}
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'AppNewsList',
  props: [],
  inject: ['news'],
};
</script>
<style lang="scss">
</style>
