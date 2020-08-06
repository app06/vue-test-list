<template>
  <div id="app">
    <b-container><list></list></b-container>
  </div>
</template>

<script>
import List from '@/components/List.vue';

import 'bootstrap/dist/css/bootstrap.css';
import 'bootstrap-vue/dist/bootstrap-vue.css';

export default {
  name: 'App',
  components: {
    List
  }
};
</script>

<style>
#app {
  padding-top: 20px;
}
</style>
