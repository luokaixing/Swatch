<!--  -->
<template>
  <div>
    <loading :imgs="imgs"
             ref="loading"></loading>
    <transition name="fade">
      <landing v-show="pageIndex===0"
               @dumpIndex="dumpIndex"></landing>
    </transition>
    <transition name="fade">
      <start v-show="pageIndex===1"
             @dumpIndex="dumpIndex"></start>
    </transition>
    <transition name="fade">
      <shopping v-show="pageIndex===2"
                @dumpIndex="dumpIndex"></shopping>
    </transition>
    <transition name="fade">
      <ending v-show="pageIndex===3"
              @dumpIndex="dumpIndex"></ending>
    </transition>
    <transition name="fade">
      <success v-show="pageIndex===4"
               @dumpIndex="dumpIndex"></success>
    </transition>
  </div>
</template>

<script>
import loading from "./loading";
import landing from "./landing";
import start from "./start";
import shopping from "./shopping";
import ending from "./ending";
import success from "./success";

export default {
  data() {
    return {
      pageIndex: 0,
      imgs: [
        require("../assets/self-bg.jpg"),
        require("../assets/active.png"),
        require("../assets/back.png"),
        require("../assets/bg.png"),
        require("../assets/check.png"),
        require("../assets/close.png"),
        require("../assets/go.png"),
        require("../assets/watch.png"),
        require("../assets/icon-1.png"),
        require("../assets/icon-2.png"),
        require("../assets/icon-3.png"),
        require("../assets/icon-4.png"),
        require("../assets/poster.png"),
        require("../assets/self-bottom.png"),
        require("../assets/stop-1.png"),
        require("../assets/stop-2.png"),
        require("../assets/stop-3.png"),
        require("../assets/submit.png"),
        require("../assets/text-bg.png")
      ]
    };
  },
  components: {
    loading,
    landing,
    shopping,
    ending,
    start,
    success
  },
  methods: {
    dumpIndex(index) {
      this.pageIndex = index;
    }
  }
};
</script>

<style lang='scss' scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>
