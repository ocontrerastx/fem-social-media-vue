<template>
  <div>
    <div class="header">
      <div class="header__title">Social Media Followers</div>
      <div class="header__total__followers">Total Followers: 23,004</div>
    </div>
    <div class="followers">
      <div v-for="(f, index) in followers" v-bind:key="index">
        <FollowerItem v-bind:f="f" />
      </div>
    </div>
  </div>
</template>

<script>
import FollowerItem from "./FollowerItem.vue";

export default {
  name: "Followers",
  props: ["followers"],
  components: {
    FollowerItem
  }
}
</script>

<style scoped lang="scss">
$light-background-top-pale-blue: hsl(225, 100%, 98%);
$light-text-dark-grayish-blue: hsl(228, 12%, 44%);

// .top__background {
//   position: absolute;
//   background-color: $light-background-top-pale-blue;
//   width: 100%;
//   height: 244px;
//   border-radius: 0 0 25px 25px;
// }

.header {
  margin-top: 38px;
}

.header__title {
  font-size: 26px;
  font-weight: 700;
}

.header__total__followers {
  margin-bottom: 46px;
  color: $light-text-dark-grayish-blue;
}

.followers {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 30px;
  margin-bottom: 48px;
}

@media screen and (max-width: 1180px) {
  .followers {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media screen and (max-width: 600px) {
  .followers {
    grid-template-columns: 1fr;
  }

  .header__title {
    font-size: 20px;
  }
}
</style>