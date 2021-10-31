<script>
import Vue from "vue";
import VueGridHelper from "@/vue-grid-helper.vue";

export default Vue.extend({
  name: "ServeDev",
  components: {
    VueGridHelper,
  },
});
</script>

<template>
  <div id="app">
    <vue-grid-helper :columns="16" :gutter="15" :containerMaxWidth="1400" />
  </div>
</template>
