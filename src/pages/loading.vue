<!-- preloading -->

<style lang='scss' type='stylesheet/scss' scoped>
.bar {
  position: absolute;
  top: 50%;
  left: 0;
  text-align: center;
  overflow: auto;
  width: 100%;
  font-size: 30px;
  color: white;
  margin-top: -100px;
  .typing_loader {
    display: block;
    margin: 0 auto;
    width: 200px;
    height: 20px;
    background-color: white;
    margin-top: 35px;
    position: relative;
  }
  .loding-line {
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    width: 0;
    background: red;
    z-index: 2;
  }

  .num {
    font-size: 30px;
    margin-top: 20px;
    display: block;
    color: #fff;
  }
}

.container {
  transition: opacity 0.4s ease;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 1;
  background: #000;
}
</style>

<template>
  <div class="container"
       v-if="showSelf"
       :style="{opacity}">
    <div class="bar">
      Loading...
      <div class="typing_loader">
        <div class="loding-line"
             :style="'width:'+((count<0?0:count)/(total)*100)+'%'"
             id="loding-line"></div>
      </div>
      <div class="num">{{parseInt((count<0?0:count)/(total)*100)}}%</div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    imgs: {
      type: Array,
      default: function() {
        return [];
      }
    }
  },
  mounted() {
    this.preLoad();
  },
  data() {
    return {
      opacity: 1,
      showSelf: true,
      count: -3,
      total: 0
    };
  },
  methods: {
    isok() {
      console.log("isok");
    },
    preLoad() {
      var queue = new createjs.LoadQueue(true);

      this.total = this.imgs.length;
      if (this.imgs.length === 0) {
        this.showSelf = false;
        this.$emit("done");
      }

      queue.on("fileload", handleFileLoad, this);
      queue.on("complete", handleComplete, this);

      function handleFileLoad(e) {
        this.count++;

        if (e.result.tagName === "VIDEO") {
          let video = document.querySelector("#video");
          video.src = e.result.src;
        }
        if (e.result.tagName === "AUDIO") {
          let audio = document.querySelector("#audio");
          audio.src = e.result.src;
        }
      }

      function handleComplete(e) {
        this.count++;
        this.$emit("done");
        this.opacity = 0;
        setTimeout(() => {
          this.showSelf = false;
        }, 400);
      }

      for (let img of this.imgs) {
        let image = new Image();
        queue.loadFile(img);
      }

      queue.loadFile({
        id: "video",
        src: require("../assets/02.mp4"),
        type: createjs.AbstractLoader.VIDEO
      });

      queue.loadFile({
        id: "audio",
        src: require("../assets/music.mp3"),
        type: createjs.AbstractLoader.SOUND
      });
    }
  }
};
</script>
