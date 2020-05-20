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
$light-text-dark-grayish-blue: hsl(228, 12%, 44%);

.overview__title {
  font-size: 24px;
  font-weight: 700;
  margin-bottom: 24px;
  color: $light-text-dark-grayish-blue;
}

.overview {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 30px;
}

@media screen and (max-width: 1180px) {
  .overview {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media screen and (max-width: 600px) {
  .overview {
    grid-template-columns: 1fr;
  }
}
</style>