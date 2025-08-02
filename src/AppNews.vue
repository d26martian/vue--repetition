<template>
  <div class="card">
    <h3>{{title}}</h3>
    <button class="btn" @click="openandler">Open</button>
    <p v-if="thisIsOpen">Lorem ipsum dolor sit amet consectetur adipisicing elit.
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
      thisIsOpen: false,
    };
  },
  methods: {
    openandler() {
      this.thisIsOpen = !this.thisIsOpen;
    },
  },
};
</script>
