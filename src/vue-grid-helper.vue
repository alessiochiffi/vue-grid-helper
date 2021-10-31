<template>
  <div class="vue-grid-helper-app">
    <div class="vue-grid-helper" v-if="gridActive">
      <div class="vue-grid-helper__row" :style="{ margin: rowMargin }">
        <div v-for="(column, index) in columns" :key="index" class="col">
          <div class="col-inner" :style="{ padding: colPadding }">
            {{ index + 1 }}
          </div>
        </div>
      </div>
    </div>

    <div class="vue-grid-helper__options">
      <button @click="toggleGrid">Toggle grid</button>
    </div>
  </div>
</template>

<script>
export default /*#__PURE__*/ {
  name: "VueGridHelper",
  data() {
    return {
      columns: 12,
      gutter: 10,
      gridActive: true,
    };
  },
  computed: {
    colPadding() {
      return `0 ${this.gutter}px`;
    },
    rowMargin() {
      return `0 ${this.getGutterInverse()}px`;
    },
  },
  methods: {
    getGutterInverse() {
      return this.gutter * -1;
    },
    toggleGrid() {
      return (this.gridActive = !this.gridActive);
    },
  },
};
</script>

<style scoped lang="scss">
.vue-grid-helper {
  max-width: 1200px;
  margin: 0 auto;
  background: #eaeaea;
  text-align: center;

  &__row {
    align-items: center;
    display: flex;
    justify-content: space-between;
    width: 100%;
  }

  .col {
    &-inner {
      height: 100vh;
      width: 100%;
      background-color: rgba(255, 0, 0, 0.252);
    }
  }

  &__options {
    bottom: 0;
    position: fixed;
    right: 0;
  }
}
</style>
