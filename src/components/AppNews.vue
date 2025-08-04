<template>
  <div class="card">
    <h3>{{title}}</h3>
    <AppButton
      :color="this.isNewsOpen ? 'btn-danger' : 'btn-success'"
      @action="openHandler"
    >
      {{this.isNewsOpen ? 'Закрыть' : 'Открыть'}}
    </AppButton>
    <AppButton
      :color="'btn-danger'"
      v-if="wasRead"
      @action="$emit('unmark', id)"
    >
      Отменить прочитано
    </AppButton>
    <div v-if="isNewsOpen">
      <hr/>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.
      Reprehenderit aspernatur at voluptatum?</p>
      <AppButton
        :color="'btn-primary'"
        v-if="!wasRead"
        @action="markHandler"
      >
        Прочесть новость
      </AppButton>
      <AppNewsList />
    </div>
  </div>
</template>
<script>

import AppButton from '../ui/AppButton.vue';
import AppNewsList from '../ui/AppNewsList.vue';

export default {
  name: 'AppNews',
  // props: ['item'],
  components: {
    AppButton,
    AppNewsList,
  },
  props: {
    id: {
      type: Number,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    wasRead: {
      type: Boolean,
      required: true,
    },
    isOpen: {
      type: Boolean,
      required: true,
    },
  },
  data() {
    return {
      isNewsOpen: false,
    };
  },
  methods: {
    openHandler() {
      this.isNewsOpen = !this.isNewsOpen;

      if (this.isNewsOpen) this.$emit('opened-news');
    },
    markHandler() {
      this.isNewsOpen = false;
      this.$emit('read-news', this.id);
    },
  },
};
</script>
