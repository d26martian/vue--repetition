<template>
  <div>
    <the-header></the-header>
    <div class="container pt-1">
      <div class="row">
        <div class="card">
          <h2>Актуальные новости {{now}}</h2>
          <span>Открыто:</span>
        </div>
      </div>
      <div class="row">
        <div class="col">
          <!-- <app-news></app-news> -->
          <AppNews
            v-for="item in news"
            :key="item"
            :id="item.id"
            :title="item.title"
            :is-open="item.isOpen"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import AppNews from './AppNews.vue';

export default {
  name: 'App',
  components: {
    // 'app-news': AppNews
    // AppNews: AppNews
    AppNews,
  },
  data() {
    return {
      now: new Date().toLocaleDateString(),
      openRate: 0,
      news: [
        {
          id: Date.now(),
          title: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Corporis, saepe!',
          isOpen: false,
        },
        {
          id: Date.now(),
          title: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Numquam!',
          isOpen: false,
        },
      ],
    };
  },
};
</script>

<style lang="scss">
</style>
