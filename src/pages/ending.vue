
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
  background-color: black;
  background-position: center center;
  background-size: cover;
  @media screen and (min-height: 1400px) {
    background-position: center top;
    bottom: 5vh;
    padding-top: 60px;
  }
  padding-top: 30px;
  text-align: center;
  box-sizing: border-box;

  .title {
    font-size: 36px;
    letter-spacing: 6px;
  }
  .info {
    @media screen and (max-height: 1400px) {
      margin: 30px 50px;
    }
    margin: 50px;
    padding: 30px 0;
    box-sizing: border-box;
    background-image: url("../assets/text-bg.png");
    background-size: cover;
    .logo {
      font-size: 42px;
      letter-spacing: 6px;
    }
    .time {
      font-size: 28px;
    }
    .address {
      font-size: 24px;
    }
  }

  .center-text {
    font-size: 28px;
    letter-spacing: 2px;
  }

  .draw {
    letter-spacing: 2px;
    @media screen and (max-height: 1400px) {
      margin-top: 55px;
    }
    margin-top: 85px;
    .draw-icon {
      display: inline-block;
      vertical-align: top;
    }
    .draw-text {
      margin-left: 10px;
      line-height: 34px;
      font-size: 22px;
      letter-spacing: 2px;
    }
    .draw-rule {
      font-size: 22px;
      line-height: 2;
    }
  }

  .form {
    @media screen and (max-height: 1400px) {
      margin-top: 20px;
    }
    margin-top: 60px;
    padding: 0 70px;
    box-sizing: border-box;
    .form-item {
      display: flex;
      &:first-child {
        margin-bottom: 30px;

        @media screen and (max-height: 1200px) {
          margin-bottom: 10px;
        }
      }

      .label {
        flex: 0 0 140px;
        width: 140px;
        display: inline-block;
        vertical-align: top;
        font-size: 30px;
        line-height: 64px;
        text-align: left;

        @media screen and (max-height: 1200px) {
          line-height: 54px;
        }
      }
      .input {
        @media screen and (max-height: 1200px) {
          line-height: 54px;
          height: 54px;
        }
        flex: 1;
        line-height: 64px;
        height: 64px;
        border: solid 2px black;
        box-sizing: border-box;
        font-size: 30px;
        padding-left: 20px;
        outline: none;
        line-height: 30px;
      }
    }
  }

  .accept {
    @media screen and (max-height: 1200px) {
      margin-top: 10px;
    }
    @media screen and (max-height: 1400px) {
      margin-top: 20px;
    }
    margin-top: 40px;
    .word {
      font-size: 20px;
      line-height: 28px;
      vertical-align: top;
    }

    .check-box {
      vertical-align: top;
      width: 28px;
      height: 28px;
      border: solid 2px black;
      box-sizing: border-box;
      z-index: 2;
      background: white;
      display: inline-block;
      margin-right: 10px;
      &.checked {
        background-image: url("../assets/check.png");
        background-size: 25px 25px;
        background-repeat: no-repeat;
        background-position: center;
      }
    }
  }
}

.img-1 {
  display: block;
  margin: 0 auto;
  @media screen and (max-height: 1200px) {
    width: 400px;
  }
}
.img-2 {
  display: block;
  margin: 0 auto;
  @media screen and (max-height: 1200px) {
    width: 300px;
  }
  @media screen and (max-height: 1400px) {
    margin-top: 20px;
  }
  margin-top: 40px;
}

.img-3 {
  display: block;
  margin: 0 auto;
  @media screen and (max-height: 1200px) {
    width: 500px;
  }
  @media screen and (max-height: 1400px) {
    margin-top: 20px;
  }
  margin-top: 30px;
}

.img-4 {
  display: block;
  margin: 0 auto;
  @media screen and (max-height: 1200px) {
    width: 500px;
  }
  @media screen and (max-height: 1400px) {
    margin-top: 20px;
  }
  margin-top: 40px;
}

.self {
  text-decoration: underline;
}
</style>

<template>
  <div class="end-container page">
    <!-- <div class="title">
      <p><strong>SWATCH</strong>诚邀您身临其境</p>
      <p>感受<strong>FLYMAGIC</strong>的魅力</p>
    </div> -->
    <img src="../assets/words/1.png"
         class="img-1">
    <img src="../assets/words/2.png"
         class="img-2">
    <img src="../assets/words/3.png"
         class="img-3">
    <img src="../assets/words/4.png"
         class="img-4">
    <!-- <div class="info">
      <p class="logo"><strong>SWATCH FLYMAGIC</strong></p>
      <p class="logo">至臻专享会</p>
      <p class="time"
         style="margin-top: 28px;"><strong>2019</strong>年<strong>11</strong>月<strong>18</strong>日 <strong>19:00-21:00</strong></p>
      <p class="time"><strong>斯沃琪上海和平饭店艺术中心斯沃琪旗舰店</strong></p>
      <p class="address">(上海市黄浦区南京东路23号外滩19号)</p>
    </div>
    <div class="center-text">
      <p>即刻完善以下个人信息</p>
      <p>将有机会近距离探索<strong>FLYMAGIC</strong>的魔法之旅</p>
    </div>
    <div class="draw">
      <p>
        <img src="../assets/setting.png"
             class="draw-icon">
        <span class="draw-text">活动现场将随机抽取<strong>3位幸运观众</strong></span>
      </p>
      <p class="draw-rule">获得<strong>SWATCH编号为8</strong>的<strong>FLYMAGIC限量腕表的购买资格</strong></p>
    </div> -->

    <div class="form">
      <div class="form-item">
        <span class="label">姓名：</span>
        <input type="text"
               @blur="handleBlur"
               class="input"
               v-model="username">
      </div>
      <div class="form-item">
        <span class="label">手机号：</span>
        <input type="number"
               @blur="handleBlur"
               class="input"
               v-model="tel">
      </div>
    </div>

    <div class="accept">
      <div class="check-box"
           @click="isChecked=!isChecked"
           :class="isChecked?'checked':''"></div>
      <span class="word"><strong>SWATCH</strong>斯沃琪重视您的隐私。</span>
      <div class="word"
           style="margin-top:5px">
        <span>
          建议您充分阅读，理解并同意
          <a class="self"
             @click="showSelf=true">隐私政策</a>
          的内容。
        </span>
      </div>
    </div>

    <div class="bottom-btns">
      <img src="../assets/submit.png"
           @click="submit">
    </div>

    <transition name="fade">
      <self v-show="showSelf"
            :showSelf.sync="showSelf"></self>
    </transition>

  </div>
</template>

<script>
import axios from "axios";
import self from "./self";
export default {
  components: { self },
  data() {
    return {
      showSelf: false,
      success: false,
      isChecked: false,
      username: "",
      tel: "",
      isSubmit: false
    };
  },
  methods: {
    async submit() {
      if (this.isSubmit) {
        return;
      }
      if (!this.isChecked) {
        alert("未同意协议");
        return;
      }

      if (!this.username || !this.tel) {
        alert("请完善表单");
        return;
      }

      if (!/^1[3456789]\d{9}$/.test(this.tel)) {
        alert("手机号码有误，请重填");
        return false;
      }

      let res = await axios.post(
        "https://projects.rfistudios.com.cn/swatch/flymagic/interface/add.php",
        {
          name: this.username,
          mobile: this.tel
        }
      );

      console.log(res);

      if (+res.data.status !== 200) {
        alert(res.data.msg);
      } else {
        this.isSubmit = true;
        window.localStorage.setItem("isSubmit", 1);

        this.$emit("dumpIndex", 4);
      }
    },
    handleBlur() {
      setTimeout(function() {
        var scrollHeight =
          document.documentElement.scrollTop || document.body.scrollTop || 0;
        window.scrollTo(0, Math.max(scrollHeight - 1, 0));
      }, 100);
    }
  }
};
</script>

