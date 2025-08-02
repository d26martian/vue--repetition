<template>
  <div class="card">
    <h3>{{title}}</h3>
    <button class="btn" @click="openHandler">
      {{this.isNewsOpen ? 'Закрыть' : 'Открыть'}}
    </button>
    <p v-if="isNewsOpen">Lorem ipsum dolor sit amet consectetur adipisicing elit.
      Reprehenderit aspernatur at voluptatum?</p>
  </div>
</template>
<script>
export default {
  name: 'AppNews',
  // props: ['item'],
  props: {
    id: {
      type: Number,
      required: true,
    },
    title: {
      type: String,
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
  },
};
</script>
