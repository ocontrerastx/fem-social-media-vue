<template>
  <div class="follower__card">
    <div>{{ f["platform-name"] }}</div>
    <div>{{ f.username }}</div>
    <div class="follower__card__total">{{ f.total }}</div>
    <div class="follower__card__metric">{{ f.metric }}</div>
    <div>{{ f.delta.count }} Today</div>
  </div>
</template>

<script>
export default {
  name: "FollowerItem",
  props: ["f"]
}
</script>

<style scoped lang="scss">
$light-card-grayish-blue: hsl(227, 47%, 96%);

.follower__card {
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 216px;
  width: 256px;
  margin: 0 15px;
  background-color: $light-card-grayish-blue;
  border-radius: 5px;
  padding: 32px 0 24px;
}

.follower__card__total {
  font-size: 56px;
  font-weight: 700;
}

.follower__card__metric {
  font-size: 12px;
  letter-spacing: 5px;
  text-transform: uppercase;
}
</style>