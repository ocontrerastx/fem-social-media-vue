<template>
  <div class="follower__card follower__card--twitter">
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

// Social Media Platforms
$facebook: hsl(195, 100%, 50%);
$twitter: hsl(203, 89%, 53%);
$instagram: linear-gradient(hsl(37, 97%, 70%) to hsl(329, 70%, 58%));
$youtube: hsl(348, 97%, 39%);

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

.follower__card--facebook {
  border-top: 4px solid $facebook;
}

.follower__card--twitter {
  border-top: 4px solid $twitter;
}

.follower__card--isntagram {
  border-top: 4px solid $instagram;
}

.follower__card--youtube {
  border-top: 4px solid $youtube;
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