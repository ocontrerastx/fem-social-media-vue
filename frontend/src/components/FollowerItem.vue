<template>
  <div class="follower__card" v-bind:class="getPlatformClass(f['platform-name'])">
    <div>
      <img v-bind:src="getPlatformLogo(f['platform-name'])" />
      {{ f.username }}
    </div>
    <div class="follower__card__total">{{ f.total }}</div>
    <div class="follower__card__metric">{{ f.metric }}</div>
    <div
      class="follower__card__delta"
      v-bind:class="f.delta.count > 0 ? 'follower__card__delta--positive' : 'follower__card__delta--negative'"
    >
      <img v-bind:src="getDeltaArrowIcon(f.delta.count)" />
      {{ f.delta.count }} Today
    </div>
  </div>
</template>

<script>
export default {
  name: "FollowerItem",
  props: ["f"],
  methods: {
    getPlatformClass(name) {
      return `follower__card--${name}`
    },
    getPlatformLogo(name) {
      return require(`../assets/icon-${name}.svg`)
    },
    getDeltaArrowIcon(delta) {
      if (delta >= 0) {
        return require(`../assets/icon-up.svg`)
      } else {
        return require(`../assets/icon-down.svg`)
      }
    }
  }
}
</script>

<style scoped lang="scss">
$light-card-grayish-blue: hsl(227, 47%, 96%);

// Primary
$lime-green: hsl(163, 72%, 41%);
$bright-red: hsl(356, 69%, 56%);

// Social Media Platforms
$facebook: hsl(195, 100%, 50%);
$twitter: hsl(203, 89%, 53%);
$instagram: linear-gradient(hsl(37, 97%, 70%) to hsl(329, 70%, 58%));
$instagram: hsl(37, 97%, 70%);
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

.follower__card--instagram {
  border-top: 4px solid $instagram;
}

.follower__card--youtube {
  border-top: 4px solid $youtube;
}

.follower__card__total {
  font-size: 56px;
  font-weight: 700;
}

.follower__card__delta {
  font-weight: 700;
}

.follower__card__delta--negative {
  color: $bright-red;
}

.follower__card__delta--positive {
  color: $lime-green;
}

.follower__card__metric {
  font-size: 12px;
  letter-spacing: 5px;
  text-transform: uppercase;
}
</style>