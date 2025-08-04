<template>
  <div>
    <the-header></the-header>
    <div class="container pt-1">
      <div class="row">
        <div class="card">
          <h2>Актуальные новости {{now}}</h2>
          <span>Открыто: {{openRate}} | Прочитано: {{readRate}}</span>
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
            :was-read="item.wasRead"
            :is-open="item.isOpen"
            @opened-news="rateHandler"
            @read-news="readNewsHandler"
            @unmark="unmarkHandler"
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
      readRate: 0,
      news: [
        {
          id: Date.now(),
          title: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Corporis, saepe!',
          isOpen: false,
          wasRead: false,
        },
        {
          id: Date.now() + 1,
          title: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Numquam!',
          isOpen: false,
          wasRead: false,
        },
      ],
    };
  },
  provide() {
    return {
      news: this.news,
    };
  },
  methods: {
    rateHandler() {
      this.openRate += 1;
    },
    readNewsHandler(id) {
      const idx = this.news.findIndex((news) => news.id === id);
      this.news[idx].wasRead = true;
      this.readRate += 1;
    },
    unmarkHandler(id) {
      // const idx = this.news.findIndex(news => news.id === id)
      // this.news[idx].wasRead = false
      const currentNews = this.news.find((news) => news.id === id);
      currentNews.wasRead = false;
      this.readRate -= 1;
    },
  },
};
</script>

<style lang="scss">
</style>
