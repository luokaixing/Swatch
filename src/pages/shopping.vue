<!--  -->

<style lang='scss' scoped>
.container {
  @media screen and (max-height: 1200px) {
    background-position: center -60px;
  }
  @media screen and (max-height: 1100px) {
    background-position: center -120px;
  }
  background-position: center top;
  @media screen and (min-height: 1400px) {
    padding-top: 55vh;
  }
  padding-top: 55vh;
}

.content-warpper {
  position: fixed;
  left: 0;
  right: 0;
  @media screen and (max-height: 1200px) {
    bottom: 2vh;
  }
  bottom: 5vh;
  @media screen and (min-height: 1400px) {
    bottom: 10vh;
  }

  .shop-bottom-btns {
    @media screen and (min-height: 1200px) {
      margin-top: 50px;
    }
    // @media screen and (min-height: 1300px) {
    //   margin-top: 100px;
    // }
  }
}
.text {
  color: white;
  &.address-text,
  &.time-text {
    font-size: 28px;
    line-height: 80px;
  }

  &.content-text {
    font-size: 34px;
    line-height: 52px;
  }

  .blue-font {
    color: #6793cc;
  }
}
</style>

<template>
  <div class="container page">

    <div class="content-warpper">

      <div class="text time-text">11月1日至15日</div>

      <div class="text content-text"><strong>SWATCH</strong>诚邀您</div>
      <div class="text content-text">前往<strong class="blue-font">斯沃琪上海和平饭店艺术中心</strong></div>
      <div class="text content-text"><strong class="blue-font">斯沃琪旗舰店</strong>进行试戴</div>
      <div class="text content-text">并领取精美水洗牛仔布托特包</div>

      <div class="text address-text"><strong>地址：</strong>上海市黄浦区南京东路23号外滩19号</div>
      <div class="shop-bottom-btns">
        <img src="../assets/back.png"
             @click="dumpIndex"
             class="submit">
      </div>

    </div>

  </div>
</template>

<script>
export default {
  data() {
    return {
      active: true
    };
  },
  methods: {
    dumpIndex() {
      this.$emit("dumpIndex", 1);
    },
    toggle() {
      this.active = !this.active;
    }
  }
};
</script>
