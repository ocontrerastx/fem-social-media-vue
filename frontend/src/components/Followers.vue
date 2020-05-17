<template>
  <div class="header top__background">
    <div class="header__title">Social Media Followers</div>
    <div class="header__total__followers">Total Followers: 23,004</div>
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

.top__background {
  position: absolute;
  background-color: $light-background-top-pale-blue;
  width: 100%;
  height: 244px;
  border-radius: 0 0 25px 25px;
}

.header {
  padding: 0 165px 0;
}

.header__title {
  font-size: 26px;
  font-weight: 700;
  margin-top: 38px;
}

.header__total__followers {
  margin-bottom: 46px;
}

.followers {
  display: flex;
  justify-content: center;
}
</style>