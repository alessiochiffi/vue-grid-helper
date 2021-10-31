<template>
  <div class="vue-grid-helper-app">
    <div class="vue-grid-helper" :style="{ maxWidth: maxWidthContainer }">
      <div class="vue-grid-helper__row" :style="{ margin: rowMargin }">
        <div v-for="(column, index) in columns" :key="index" class="col">
          <div class="col-inner" :style="{ padding: colPadding }"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default /*#__PURE__*/ {
  name: "VueGridHelper",
  props: {
    columns: {
      default: 12,
      type: Number,
    },
    gutter: {
      default: 12,
      type: Number,
    },
    containerMaxWidth: {
      default: 1200,
      type: Number,
    },
  },

  computed: {
    maxWidthContainer() {
      return `${this.containerMaxWidth}px`;
    },
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
  },
};
</script>

<style scoped lang="scss">
.vue-grid-helper {
  background: #eaeaea;
  margin: 0 auto;

  &__row {
    align-items: center;
    display: flex;
    justify-content: space-between;
    width: 100%;
  }

  .col {
    &-inner {
      background-color: rgba(248, 70, 70, 0.2);
      height: 100vh;
      width: 100%;
    }
  }
}
</style>
