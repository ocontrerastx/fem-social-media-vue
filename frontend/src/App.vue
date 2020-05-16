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
@import url("https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap");

// Primary
$lime-green: hsl(163, 72%, 41%);
$bright-red: hsl(356, 69%, 56%);

// Social Media Platforms
$facebook: hsl(195, 100%, 50%);
$twitter: hsl(203, 89%, 53%);
$instagram: linear-gradient(hsl(37, 97%, 70%) to hsl(329, 70%, 58%));
$youtube: hsl(348, 97%, 39%);

// Toogle
$light-toggle: hsl(230, 22%, 74%);
$dark-toggle: linear-gradient(hsl(210, 78%, 56%) to hsl(146, 68%, 55%));

// Dark Theme
$dark-background-very-dark-blue: hsl(230, 17%, 14%);
$dark-background-top-very-dark-blue: hsl(232, 19%, 15%);
$dark-card-desaturated-blue: hsl(228, 28%, 20%);
$dark-text-desaturated-blue: hsl(228, 34%, 66%);
$dark-text-white: hsl(0, 0%, 100%);

// Light Theme
$light-background-white: hsl(0, 0%, 100%);
$light-background-top-pale-blue: hsl(225, 100%, 98%);
$light-card-grayish-blue: hsl(227, 47%, 96%);
$light-text-dark-grayish-blue: hsl(228, 12%, 44%);
$light-text-very-dark-blue: hsl(230, 17%, 14%);

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Inter, sans-serif;
  background: $light-background-white;
}
</style>
