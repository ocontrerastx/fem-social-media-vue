<template>
  <div class="header">
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

<style scoped>
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