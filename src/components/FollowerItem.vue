<template>
  <div class="follower__card" v-bind:class="`follower__card--${f['platform-name']}`">
    <div class="follower__card__identity">
      <img
        v-bind:src="require(`../assets/icon-${f['platform-name']}.svg`)"
        v-bind:alt="f['platform-name']"
      />
      {{ f.username }}
    </div>
    <div class="follower__card__total">{{ f.total | trim }}</div>
    <div class="follower__card__metric">{{ f.metric }}</div>
    <div
      class="follower__card__delta"
      v-bind:class="f.delta.count > 0 ? 'follower__card__delta--positive' : 'follower__card__delta--negative'"
    >
      <img
        v-bind:src="f.delta.count > 0 ? require(`../assets/icon-up.svg`) : require(`../assets/icon-down.svg`)"
      />
      {{ Math.abs(f.delta.count) }} Today
    </div>
  </div>
</template>

<script>
export default {
  name: "FollowerItem",
  props: ["f"],
  filters: {
    trim: function (total) {
    if (total > 9999) {
      const totalString = total.toString(); 
      return `${totalString.substr(0,2)}k`
    }
    return total;
  }
    }
  }

</script>

<style scoped lang="scss">
.follower__card {
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 216px;
  width: 256px;
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

.follower__card--instagram::before {
  content: "";
  border-radius: 5px 5px 0 0;
  display: block;
  height: 4px;
  width: 100%;
  position: absolute;
  top: 0;
  left: 0;
  background: $instagram;
}

.follower__card--instagram {
  position: relative;
}

.follower__card--youtube {
  border-top: 4px solid $youtube;
}

.follower__card__identity {
  display: flex;
  align-items: center;
  margin-bottom: 18px;
  font-size: 12px;
}

.follower__card__identity > img {
  margin-right: 8px;
}

.follower__card__total {
  font-size: 56px;
  font-weight: 700;
}

.follower__card__delta {
  font-size: 12px;
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
  margin-bottom: 25px;
}
</style>