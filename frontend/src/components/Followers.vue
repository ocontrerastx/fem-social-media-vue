<template>
  <div>
    <div class="header">
      <div class="header__text">
        <div class="header__text__title">Social Media Followers</div>
        <div class="header__text__total__followers">Total Followers: 23,004</div>
      </div>
      <div class="theme__toggle">
        <input type="checkbox" id="toggle" class="checkbox" />
        <label for="toggle" class="switch"></label>
      </div>
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
.header {
  margin-top: 38px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.header__text__title {
  font-size: 26px;
  font-weight: 700;
}

.switch {
  position: relative;
  display: inline-block;
  width: 48px;
  height: 25px;
  background-color: $light-toggle;
  border-radius: 20px;
}

.switch::after {
  content: "";
  position: absolute;
  width: 18px;
  height: 18px;
  border-radius: 50%;
  background-color: white;
  top: 3px;
  left: 3px;
  transition: all 0.3s;
}

.checkbox:checked + .switch::after {
  left: 26px;
}
.checkbox:checked + .switch {
  background: $dark-toggle;
}

.checkbox {
  display: none;
}

.header__text__total__followers {
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