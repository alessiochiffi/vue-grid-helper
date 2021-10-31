<script>
import Vue from 'vue';
import VueGridHelper from '@/vue-grid-helper.vue';

export default Vue.extend({
  name: 'ServeDev',
  components: {
    VueGridHelper
  }
});
</script>

<template>
  <div id="app">
    <vue-grid-helper />
  </div>
</template>
