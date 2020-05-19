<template>
  <div>
    <div class="overview__title">Overview - Today</div>
    <div class="overview">
      <div v-for="(o, index) in overview" v-bind:key="index">
        <OverviewItem v-bind:o="o" />
      </div>
    </div>
  </div>
</template>

<script>
import OverviewItem from "./OverviewItem.vue";

export default {
  name: "Overview",
  props: ["overview"],
  components: {
    OverviewItem
  }
}
</script>

<style scoped lang="scss">
.overview__title {
  font-size: 24px;
  font-weight: 700;
  margin-bottom: 24px;
}

.overview {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  width: 1150px;
  // margin: 0 165px 0;
}
</style>