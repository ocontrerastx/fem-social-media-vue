<template>
  <div class="header">
    <div class="title">Social Media Followers</div>
    <div>Total Followers: 23,004</div>
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
.title {
  font-size: 26px;
  margin-top: 38px;
}

.followers {
  display: flex;
  justify-content: center;
}
</style>