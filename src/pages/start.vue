<!--  -->

<style lang='scss' type='stylesheet/scss' scoped>
.content {
  text-align: center;
  .word {
    font-size: 44px;
    line-height: 88px;
    color: white;
    .logo-text {
      color: #6793cc;
      font-weight: bold;
    }
  }

  .text {
    font-size: 30px;
    line-height: 1.5;
    color: white;
  }
}

.home-container {
  background-position: center top;
  background-image: url("../assets/watch2.png");
  background-color: #030304;
  background-repeat: no-repeat;
  @media screen and (max-height: 1100px) {
    background-position: center -100px;
  }
  .content-warpper {
    position: fixed;
    bottom: 5vh;
    left: 0;
    right: 0;
    @media screen and (min-height: 1400px) {
      bottom: 10vh;
    }

    @media screen and (min-height: 1400px) {
      margin-top: 15vh;
    }
    .home-bottom-btns {
      text-align: center;
      margin-top: 40px;

      @media screen and (min-height: 1200px) {
        margin-top: 80px;
      }

      @media screen and (min-height: 1400px) {
        // margin-top: 160px;
      }
      img + img {
        margin-left: 60px;
      }
    }
  }
}
</style>

<template>
  <div class="home-container page">

    <div class="content-warpper">
      <div class="content">
        <div class="word">解密<span class="logo-text">FLYMAGIC</span>的魔法</div>
        <div class="text">
          三枚编号为“8” 的SWATCH FLYMAGIC<br />
          现于和平饭店艺术中心尊荣展出<br />
          敬请莅临鉴赏试戴
        </div>
      </div>
      <div class="home-bottom-btns">
        <img src="../assets/go.png"
             @click="dumpIndex(2)">
        <img src="../assets/active.png"
             @click="dumpIndex(3)">
      </div>
    </div>
  </div>
</template>

<script type='text/ecmascript-6'>
export default {
  data() {
    return {};
  },
  methods: {
    dumpIndex(index) {
      // if (index === 3 && +window.localStorage.getItem("isSubmit") === 1) {
      //   this.$emit("dumpIndex", 4);
      //   return;
      // }
      this.$emit("dumpIndex", index);
    }
  }
};
</script>
