<template>
  <div id="app">
    <router-view />
  </div>
</template>

<script>
import vueTouch from "@/js/vueTouch.js";
export default {
  name: "App"
};
</script>

<style lang="scss"  type='stylesheet/scss'>
.page {
  position: fixed;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
}
.container {
  height: 100vh;
  background-image: url("./assets/watch.png");
  background-repeat: no-repeat;
  background-color: #030304;
  background-position: center -60px;
  @media screen and (min-height: 1400px) {
    background-position: center top;
    bottom: 5vh;
  }
  text-align: center;
  box-sizing: border-box;
}

.bottom-btns {
  text-align: center;
  position: absolute;
  margin: 0 auto;
  left: 0;
  right: 0;
  bottom: 2vh;

  @media screen and (min-height: 1400px) {
    bottom: 5vh;
  }

  img + img {
    margin-left: 64px;
  }
}
</style>
