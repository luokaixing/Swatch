
<style lang='scss' scoped>
.landing {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  .video-one {
    .video {
      object-fit: cover;
      width: 100vw;
      height: 100vh;
    }
  }
}

p {
  margin: 0;
  line-height: 1.5;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}

.move-left-enter-active,
.move-left-leave-active {
  transition: transform 0.6s, opacity 1s;
}
.move-left-enter,
.move-left-leave-to {
  // transform: translateX(-600px);
  opacity: 0;
}

.move-right-enter-active,
.move-right-leave-active {
  transition: transform 0.3s;
  transition: transform 0.6s, opacity 1s;
}
.move-right-enter,
.move-right-leave-to {
  // transform: translateX(600px);
  opacity: 0;
}
.mask {
  border-radius: 10px;
  letter-spacing: 6px;
  position: fixed;
  bottom: 5vh;
  left: 50%;
  z-index: 999;
  transform: translateX(-50%);
  color: white;
  font-size: 40px;
  // font-weight: 700;
  width: 80%;
  text-align: center;
  // padding: 20px 0 60px 0;
  // background: rgba(0, 0, 0, 1);
}

.content {
  position: absolute;
  bottom: 10vh;
  color: white;
  text-align: center;
  left: 0;
  right: 0;
  letter-spacing: 4px;
  h1 {
    font-size: 50px;
    line-height: 1.5;
    margin: 0;
    margin-bottom: 40px;
  }
  div {
    margin: 0;
    font-size: 40px;
    line-height: 1.5;
  }
}

.title {
  letter-spacing: 4px;
  font-size: 30px;
  line-height: 1.5;
  margin: 0;
  margin-bottom: 40px;
  font-weight: normal;
}

.stop-1 {
  position: fixed;
  top: 20vh;
  right: 20px;
}

.stop-2 {
  position: fixed;
  top: 20vh;
  left: 20px;
}

.stop-3 {
  position: fixed;
  top: 10vh;
  left: 20px;
}
.mute-icon {
  position: fixed;
  z-index: 4;
  right: 30px;
  top: 30px;
  width: 50px;
  height: 50px;
}
</style>

<!--
上滑浮层：0s
倒转浮层：6s
齿轮浮层：10s
晃动浮层：16s
-->

<!--  -->
<template>
  <!-- @click="activeIndex===-2?activeIndex=-3:activeIndex=-2" -->
  <div class="landing page"
       @touchstart="touchStart"
       @touchmove="touchMove">
    <transition name="fade">
      <img :src="isMute?require('../assets/mute.png'):require('../assets/not-mute.png')"
           v-if="activeIndex!==0"
           @click.stop="setMute"
           class="mute-icon">
    </transition>
    <div class="video-one">
      <!-- @ended="watchEndAudio" -->
      <audio src=""
             ref="audio"
             id="audio"></audio>
      <video src=""
             @ended="watchEndVideo"
             poster="@/assets/poster.png"
             preload="auto"
             muted
             id="video"
             ref="video"
             class="video"
             playsinline
             webkit-playsinline="true"
             x5-video-player-type="h5"></video>
    </div>
    <div>
      <transition name="fade">
        <div class="mask"
             v-if="activeIndex===0">
          <img src="../assets/icon-1.png">
          <h1 class="title">开启<strong>SWATCH FLYMAGIC</strong>品鉴之旅</h1>
          <!-- <p>往上滑动打开玻璃罩 </p>
          <p>解除<strong>魔法</strong>屏障</p> -->
        </div>
      </transition>

      <transition name="move-right">
        <!-- <div class="content"
             v-if="activeIndex===-2"> -->
        <!-- <h1>镜像翻转魔法</h1>
          <div>机芯反转及镂空轮系构造</div>
          <div>往上滑动打开玻璃罩</div>
          <div>藏在表镜背后的神秘时间魔法</div> -->
        <img src="../assets/stop-1.png"
             v-if="activeIndex===-2"
             class="stop-1">
        <!-- </div> -->
      </transition>

      <transition name="move-left">
        <!-- <div class="content" -->
        <img src="../assets/stop-2.png"
             class="stop-2"
             v-if="activeIndex===-3">
        <!-- <h1>时光倒流魔法</h1>
          <div><strong>FLYMAGIC</strong>全新秒针倒转设计</div>
          <div>给你时光倒流般的魔法体验</div> -->
        <!-- </div> -->
      </transition>

      <transition name="move-left">
        <!-- <div class="content" -->
        <img src="../assets/stop-3.png"
             class="stop-3"
             v-if="activeIndex===-4">
        <!-- <h1>精准计时魔法</h1>
          <div>新型顺磁性<strong>Nivachron ™</strong>游丝的诞生</div>
          <div>为精准计时魔法提供了新的可能</div>
          <div>从此，分秒必争</div> -->
        <!-- </div> -->
      </transition>

      <transition name="fade">
        <div class="mask"
             v-if="activeIndex===1">
          <img src="../assets/icon-2.png">
          <!-- <p>请将手机倒转</p> -->
        </div>
      </transition>
      <transition name="fade">
        <div class="mask"
             v-if="activeIndex===2">
          <transition name="rotate">
            <img src="../assets/icon-3.png">
          </transition>
          <!-- <p>请转动齿轮</p> -->
        </div>
      </transition>
      <transition name="fade">
        <div class="mask"
             v-if="activeIndex===3">
          <img src="../assets/icon-4.png">
          <!-- <p>请左右摇晃手机</p> -->
        </div>
      </transition>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      x: null,
      y: null,
      activeIndex: 0,
      needPrePlay: true,
      firstDuration: 6500,
      secDuration: 10600,
      thiDuration: 16200,
      interVal: null,
      volumn: 0.01,
      isMute: false
    };
  },
  watch: {
    isMute(newData) {
      if (newData) {
        // this.interVal = setInterval(() => {
        //   if (this.volumn > 0.02) {
        //     this.volumn -= 0.02;
        //     this.$refs.audio.volume = this.volumn;
        //   } else {
        //     clearInterval(this.interVal);
        this.$refs.audio.pause();
        // }
        // }, 10);
      } else {
        this.$refs.audio.play();
        this.interVal = setInterval(() => {
          if (this.volumn < 0.98) {
            this.volumn += 0.02;
            this.$refs.audio.volume = this.volumn;
          } else {
            clearInterval(this.interVal);
          }
        }, 10);
      }
    }
  },
  methods: {
    setMute() {
      this.isMute = !this.isMute;
      localStorage.setItem("isMute", this.isMute ? 1 : 0);
    },
    playAudio() {
      clearInterval(this.interVal);
      this.$refs.audio.volume = this.volumn;
      if (this.isMute) {
        return;
      }
      this.$refs.audio.play();

      this.interVal = setInterval(() => {
        if (this.volumn < 0.98) {
          this.volumn += 0.02;
          this.$refs.audio.volume = this.volumn;
        } else {
          clearInterval(this.interVal);
        }
      }, 10);
    },
    pauseAudio() {
      clearInterval(this.interVal);
      this.interVal = setInterval(() => {
        if (this.volumn > 0.02) {
          this.volumn -= 0.02;
          this.$refs.audio.volume = this.volumn;
        } else {
          clearInterval(this.interVal);
          this.$refs.audio.pause();
        }
      }, 10);
    },
    watchEndAudio() {
      this.pauseAudio();
      this.playAudio();
    },
    watchEndVideo() {
      this.pauseAudio();
      this.$emit("dumpIndex", 1);
    },
    touchStart(e) {
      if (this.activeIndex !== 0 && this.activeIndex !== 2) {
        return;
      }

      let point = e.targetTouches[0];

      this.y = point.clientY;
      this.x = point.clientX;
    },
    touchMove(e) {
      if (this.activeIndex !== 0 && this.activeIndex !== 2) {
        return;
      }
      let point = e.targetTouches[0];
      let moveY = point.clientY;
      let moveX = point.clientX;

      // 上划
      if (this.activeIndex === 0) {
        if (moveY - this.y < -100) {
          this.activeIndex = -1;
          this.playVideo();
          this.playAudio();

          setTimeout(() => {
            this.pauseVideo();
            this.activeIndex = 1;
          }, this.firstDuration);
        }
      }

      if (this.activeIndex === 2) {
        if (
          Math.sqrt(Math.pow(moveX - this.x, 2) + Math.pow(moveY - this.y, 2)) >
          100
        ) {
          this.activeIndex = -3;
          this.playVideo();

          setTimeout(() => {
            this.pauseVideo();
            this.activeIndex = 3;
          }, this.thiDuration - this.secDuration);
        }
      }
    },
    pauseVideo() {
      this.$refs.video.pause();
    },
    playVideo() {
      this.$refs.video.play();
    }
  },
  mounted() {
    this.isMute = +localStorage.getItem("isMute") === 1;
    //运动事件监听
    if (window.DeviceMotionEvent) {
      window.addEventListener("devicemotion", deviceMotionHandler, false);
    }

    //获取加速度信息
    //通过监听上一步获取到的x, y, z 值在一定时间范围内的变化率，进行设备是否有进行晃动的判断。
    //而为了防止正常移动的误判，需要给该变化率设置一个合适的临界值。
    var SHAKE_THRESHOLD = 4000;
    var last_update = 0;
    var x,
      y,
      z,
      last_x = 0,
      last_y = 0,
      last_z = 0;
    const _this = this;
    let loged = true;

    function setWechatShareText(wechatShareText) {
      wx.ready(function() {
        //自定义微信分享内容功能
        wx.onMenuShareTimeline({
          title: wechatShareText.title,
          link: wechatShareText.link,
          imgUrl: wechatShareText.imgUrl,
          success: function() {}
        });
        wx.onMenuShareAppMessage({
          title: wechatShareText.title,
          desc: wechatShareText.desc,
          link: wechatShareText.link,
          imgUrl: wechatShareText.imgUrl,
          type: "",
          dataUrl: "",
          success: function() {}
        });
      });
    }

    axios
      .get(
        "https://projects.rfistudios.com.cn/swatch/flymagic/wechat.php?url=" +
          encodeURIComponent(window.location.href.split("#")[0])
      )
      .then(data => {
        data = data.data;

        console.log(data);

        wx.config({
          debug: false,
          appId: data.appId,
          timestamp: data.timestamp,
          nonceStr: data.nonceStr,
          signature: data.signature,
          jsApiList: ["onMenuShareTimeline", "onMenuShareAppMessage"]
        });

        wx.ready(function() {
          _this.$refs.video.play();
          _this.$refs.video.pause();
          _this.$refs.audio.play();
          _this.$refs.audio.pause();

          let wechatShareText = {
            title: "诚邀您出席SWATCH FLYMAGIC至臻专享会",
            desc: "前来体验SWATCH FLYMAGIC的革新突破！",
            link: data.url,
            imgUrl:
              "https://projects.rfistudios.com.cn/swatch/flymagic/share.png"
          };

          setWechatShareText(wechatShareText);
        });
      });

    function deviceMotionHandler(eventData) {
      // 摇一摇
      var acceleration = eventData.accelerationIncludingGravity;
      var curTime = new Date().getTime();
      if (curTime - last_update > 10) {
        var diffTime = curTime - last_update;
        last_update = curTime;
        x = acceleration.x;
        y = acceleration.y;
        z = acceleration.z;
        var speed =
          (Math.abs(x + y + z - last_x - last_y - last_z) / diffTime) * 10000;
        if (speed > SHAKE_THRESHOLD && _this.activeIndex === 3) {
          _this.activeIndex = -4;
          _this.playVideo();

          // setTimeout(() => {
          //   _this.pauseVideo();
          //   _this.activeIndex = 3;
          // }, 10000);
        }
        last_x = x;
        last_y = y;
        last_z = z;
      }
      // 倒立
      var accGravity = eventData.accelerationIncludingGravity;
      if (accGravity.y > 9 && _this.activeIndex === 1) {
        _this.activeIndex = -2;
        _this.playVideo();

        setTimeout(() => {
          _this.pauseVideo();
          _this.activeIndex = 2;
        }, _this.secDuration - _this.firstDuration);
      }
    }
  }
};
</script>