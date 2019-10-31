
<style lang="scss" scoped>
p {
  margin: 0;
}
.end-container {
  color: white;
  line-height: 1.5;

  height: 100vh;
  background-image: url("../assets/bg.png");
  background-repeat: no-repeat;
  background-color: #030304;
  background-position: center center;
  background-size: cover;
  @media screen and (min-height: 1400px) {
    background-position: center top;
    bottom: 5vh;
  }
  padding-top: 20vh;
  text-align: center;
  box-sizing: border-box;

  .title {
    font-size: 50px;
    line-height: 2;
    color: white;
    letter-spacing: 6px;
  }
  .bottom {
    font-size: 54px;
    line-height: 2;
    color: white;
    letter-spacing: 6px;
    margin-top: 30vh;
  }
}

#watch {
  margin-top: 10vh;
  margin-bottom: 15vh;
}

.text-content {
  position: absolute;
  bottom: 50%;
  transform: translateY(50%);
  left: 0;
  right: 0;
}
</style>

<template>
  <div class="end-container page">
    <!-- <div class="title">
      <div>
        您的信息已提交成功，
      </div>
      <div>
        敬请期待！
      </div>
    </div>

    <div class="bottom">
      <div>
        魔法之旅如期而至
      </div>
      <div><strong>SWATCH</strong>静候您的光临</div>

    </div> -->

    <div class="text-content">
      <!-- <img src="../assets/words/5.png"
           id="success">
      <img src="../assets/words/6.png"
           id="watch"> -->
      <img src="../assets/words/8.png"
           id="success-bottom">
    </div>

  </div>
</template>


