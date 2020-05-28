<template>
  <div id="app">
    <Followers v-bind:followers="followers" />
    <Overview v-bind:overview="overview" />
  </div>
</template>

<script>
import Followers from "./components/Followers.vue";
import Overview from "./components/Overview.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    Followers,
    Overview,
  },
  data() {
    return {
      followers: [],
      overview: [],
    };
  },
  created() {
    axios
      .get("https://5ecefd5b61c8480016701b1f.mockapi.io/followers")
      .then((response) => {
        this.followers = response.data;
      })
      .catch((e) => {
        this.errors.push(e);
      }),
      axios
        .get("https://5ecefd5b61c8480016701b1f.mockapi.io/overview")
        .then((response) => {
          this.overview = response.data;
        })
        .catch((e) => {
          this.errors.push(e);
        });
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap");

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Inter, sans-serif;
  background: $light-background-white;
  color: $light-text-very-dark-blue;
}

#app::before {
  content: "";
  z-index: -1;
  top: 0;
  left: 0;
  background-color: $light-background-top-very-pale-blue;
  width: 100%;
  height: 244px;
  position: absolute;
  border-radius: 0 0 25px 25px;
}

#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
  z-index: 3;
}

@media screen and (max-width: 600px) {
  #app::before {
    display: none;
  }
}
</style>
