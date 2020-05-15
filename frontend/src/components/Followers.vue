<template>
  <div>
    <h1>Social Media Followers</h1>
    <div v-for="(f, index) in followers" v-bind:key="index">
      <FollowerItem v-bind:f="f" />
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
</style>