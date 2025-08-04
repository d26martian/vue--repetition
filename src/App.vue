<template>
  <div>
    <div class="container">
      <div class="row">
        <div class="card mb-3">
          <h2>динамические и синхронные компоненты</h2>
          <div class="btn-group">
            <AppButton
              :color="oneColor"
              @action="active = 'one'"
            >
              One
            </AppButton>
            <AppButton
              :color="twoColor"
              @action="active = 'two'"
            >
              Two
            </AppButton>
          </div>
        </div>
        <hr>
        <keep-alive>
          <component :is="componentName"></component>
        </keep-alive>
      </div>
    </div>
  </div>
</template>

<script>
import AppButton from './ui/AppButton.vue';
import AppTextOne from './ui/AppTextOne.vue';
import AppTextTwo from './ui/AppTextTwo.vue';

export default {
  name: 'App',
  components: {
    AppButton,
    AppTextOne,
    AppTextTwo,
  },
  data() {
    return {
      active: 'one',
    };
  },
  computed: {
    componentName() {
      // if(this.active === 'one') {
      //   return 'AppTextOne'
      // }
      // return 'AppTextTwo'
      return `app-text-${this.active}`;
    },
    oneColor() {
      return this.active === 'one' ? 'btn-primary' : '';
    },
    twoColor() {
      return this.active === 'two' ? 'btn-success' : '';
    },
  },
  methods: {},
};
</script>

<style lang="scss">
</style>
