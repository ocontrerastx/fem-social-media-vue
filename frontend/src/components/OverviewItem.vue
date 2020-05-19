<template>
  <div class="overview__card">
    <div class="overview__card__metric">
      {{ o.metric }}
      <img v-bind:src="require(`../assets/icon-${o['platform-name']}.svg`)" />
    </div>
    <div class="overview__card__total">{{ o.total }}</div>
    <div
      class="overview__card__delta"
      v-bind:class="o.delta.percentage > 0 ? 'overview__card_delta--positive' : 'overview__card_delta--negative'"
    >
      <img
        v-bind:src="o.delta.percentage > 0 ? require(`../assets/icon-up.svg`) : require(`../assets/icon-down.svg`)"
      />
      {{ Math.abs(o.delta.percentage) }}%
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
$light-card-grayish-blue: hsl(227, 47%, 96%);

// Primary
$lime-green: hsl(163, 72%, 41%);
$bright-red: hsl(356, 69%, 56%);

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
}

.overview__card__total {
  font-size: 30px;
  font-weight: 700;
}

.overview__card__delta {
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