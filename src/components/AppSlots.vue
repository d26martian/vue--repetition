<template>
  <div>
    <the-header></the-header>
    <div class="container">
      <div class="row">
        <div class="card mb-3">
          <h2>Topic SLOTS</h2>
          <hr/>
        </div>
        <AppBlock>
          <p>Lorem, ipsum dolor sit amet consectetur adipisicing.</p>
          <!-- <template v-slot:header>
            <h3>Simple title!</h3>
          </template> -->
          <template #header>
            <h3>Simple title!</h3>
          </template>
          <template #footer>
            <hr />
            <small>This is footer!</small>
          </template>
        </AppBlock>
        <AppList>
          <template #default="slotProps">
            <strong>{{slotProps.idxSlot}}</strong>
            <span style="color: #c25205;">Item: {{slotProps.itemSlot}}</span>
          </template>
        </AppList>
      </div>
    </div>
  </div>
</template>

<script>
import AppBlock from '../ui/AppBlock.vue';
import AppList from '../ui/AppList.vue';

export default {
  name: 'App',
  components: {
    AppBlock,
    AppList,
  },
  data() {
    return {};
  },
  methods: {},
};
</script>

<style lang="scss">
</style>
