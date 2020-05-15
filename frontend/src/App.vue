<template>
  <div id="app">
    <Followers v-bind:followers="followers" />
  </div>
</template>

<script>
import Followers from "./components/Followers.vue";
import axios from 'axios';
export default {
  name: "App",
  components: {
    Followers
  },
  data() {
    return {
      followers: [],
      overview: [],
    }
  },
  created() {
    axios.get('http://localhost:3000/followers')
    .then(response => {
      this.followers = response.data
    })
    .catch(e => {
      this.errors.push(e)
    })
  },


};
</script>

<style lang="scss">
</style>
