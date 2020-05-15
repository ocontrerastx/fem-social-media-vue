<template>
  <div>
    <div>{{ f.metric }}</div>
    <div>{{ f["platform-name"] }}</div>
    <div>{{ f.total }}</div>
    <div>{{ f.delta.count }}</div>
    <div>{{ f.username }}</div>
  </div>
</template>

<script>
export default {
  name: "FollowerItem",
  props: ["f"]
}
</script>

<style scoped>
</style>