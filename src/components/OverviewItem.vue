<template>
  <div class="overview__card">
    <div class="overview__card__metric">
      {{ o.metric }}
      <img v-bind:src="require(`../assets/icon-${o['platform-name']}.svg`)" />
    </div>
    <div class="overview__card__totals">
      <div class="overview__card__totals__total">{{ o.total }}</div>
      <div
        class="overview__card__totals__delta"
        v-bind:class="o.delta.percentage > 0 ? 'overview__card_delta--positive' : 'overview__card_delta--negative'"
      >
        <img
          v-bind:src="o.delta.percentage > 0 ? require(`../assets/icon-up.svg`) : require(`../assets/icon-down.svg`)"
        />
        {{ Math.abs(o.delta.percentage) }}%
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "OverviewItem",
  props: ["o"],
}
</script>

<style scoped lang="scss">
.overview__card {
  border-radius: 5px;
  padding: 26px 24px 30px 20px;
  width: 254px;
  height: 124px;
  background: $light-card-grayish-blue;
}

.overview__card__metric {
  font-size: 14px;
  font-weight: 700;
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 22px;
}

.overview__card__totals {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
}

.overview__card__totals__total {
  font-size: 30px;
  font-weight: 700;
}

.overview__card__totals__delta {
  font-size: 12px;
  font-weight: 700;
}

.overview__card_delta--negative {
  color: $bright-red;
}

.overview__card_delta--positive {
  color: $lime-green;
}
</style>