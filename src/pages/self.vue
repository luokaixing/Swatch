<!--  -->

<style lang='scss' type='stylesheet/scss' scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
.self-container {
  position: fixed;
  z-index: 3;
  background: rgba(22, 27, 39, 0.8);
  padding: 55px 30px;
  box-sizing: border-box;
  top: 70px;
  left: 60px;
  right: 70px;
  bottom: 60px;
  display: flex;
  .content {
    flex: 1;
    font-size: 16px;
    text-align: left;
    background-image: url("../assets/self-bg.jpg");
    display: flex;
    flex-direction: column;
    padding: 40px 30px;
    box-sizing: border-box;
    position: relative;
    .title {
      flex: 0 0 26px;
      font-size: 26px;
      letter-spacing: 6px;
      text-align: center;
      margin-bottom: 30px;
    }
    .text {
      flex: 1;
      height: 100%;
      overflow-y: auto;
      font-size: 16px;
      padding-bottom: 60px;
    }
    .self-bottom {
      position: absolute;
      left: 0;
      right: 0;
      bottom: 30px;
    }
  }
}
.close {
  position: absolute;
  right: 15px;
  top: 15px;
}
</style>

<template>
  <div class="self-container">
    <img src="../assets/close.png"
         @click="close"
         class="close">
    <div class="content">
      <div class="title">
        隐私政策
      </div>
      <div class="text"
           v-html="text">
      </div>
      <img src="../assets/self-bottom.png"
           class="self-bottom">
    </div>
  </div>
</template>

<script type='text/ecmascript-6'>
export default {
  props: ["showSelf"],
  methods: {
    close() {
      this.$emit("update:showSelf", false);
    }
  },
  data() {
    return {
      text: `

本隐私政策描述了在发布了本隐私政策的网站和应用程序上（无论是发布于我们的数字资产之上还是我们在第三方网站或平台上提供的应用程序之上），我们深知个人信息对您的重要性，并将按照法律法规要求和业界成熟的安全标准，采取相应的安全保护措施来保护您的个人信息。我们希望通过本隐私政策向您清晰地介绍在使用我们的产品/服务时，我们如何处理您的个人信息，以及我们为您提供的访问、更正、删除和保护这些信息的方式。<br/>
本政策将帮助您了解以下内容：<br/>
1、我们如何收集和使用您的个人信息<br/>
2、我们如何使用 Cookie 和同类技术<br/>
3、我们如何共享、转让、公开披露您的个人信息<br/>
4、我们如何保存和保护您的个人信息<br/>
5、您如何管理您的个人信息<br/>
6、未成年人的个人信息保护<br/>
7、通知和修订<br/>
8、如何联系我们<br/>
9、附录<br/>
【特别提示】请您在使用我们提供的各项产品/服务前，仔细阅读并充分理解本《隐私政策》（重点内容我们已将字体加粗请您特别关注）并作出相应选择。一旦您使用或继续使用我们的产品/服务时，即意味着您同意我们按照本隐私政策处理您的相关信息。<br/>
如对本隐私政策有任何疑问，您可以通过本隐私政策“如何联系我们”中提供的方式与我们联系） 。<br/>
一、我们如何收集和使用您的个人信息<br/>
1、在您使用我们的产品/服务时，您需要/可以选择授权我们收集和使用个人信息的场景包括：<br/>
（1）为了向您提供我们产品/服务的基本功能，您需要授权我们收集、使用必要信息的情形（如姓名、手机号等），如您拒绝提供前述必要信息，您将无法正常使用我们的的产品/服务；<br/>
（2）为了向您提供我们产品/服务的拓展功能，您可以选择授权我们收集、使用信息的情形，如您拒绝提供前述信息，您将无法正常使用相关附加功能或无法实现我们拟达到的功能效果，但并不会影响您正常使用我们产品/服务的基本功能。  <br/>
2、请您知悉，以下情形中，我们收集、使用个人信息无需征得您的授权同意：<br/>
（1）与国家安全、国防安全有关的；<br/>
（2）与公共安全、公共卫生、重大公共利益有关的；<br/>
（3）与犯罪侦查、起诉、审判和判决执行等有关的；<br/>
（4）出于维护个人信息主体或其他个人的生命、财产等重大合法权益但又很难得到本人同意的；<br/>
（5）所收集的个人信息是个人信息主体自行向社会公众公开的；<br/>
（6）从合法公开披露的信息中收集的您的个人信息的，如合法的新闻报道、政府信息公开等渠道；<br/>
（7）用于维护所提供的产品与/或服务的安全稳定运行所必需的，例如发现、处置产品与/或服务的故障；<br/>
（8）为合法的新闻报道所必需的；<br/>
（9）学术研究机构基于公共利益开展统计或学术研究所必要，且对外提供学术研究或描述的结果时，对结果中所包含的个人信息进行去标识化处理的；<br/>
（10）法律法规规定的其他情形。<br/>
请注意，单独或与其他信息相结合无法识别您的身份或者与您直接建立联系的信息，不属于个人信息。如果我们将单独无法与任何特定个人建立联系的信息与其他信息结合用于识别自然人个人身份，或者将其与个人信息结合使用，则在结合使用期间，此类信息将被视为个人信息。<br/>

3、我们可能会收集您在参与产品/服务调查时主动向我们提供的信息，以及您与我们的关联方、合作伙伴之间互动时提供的相关信息，以便于您追踪订单情况、发起用户投诉以及我们优化客户服务的质量与流程。<br/>
 
4、我们可能将业务中收集的个人信息用于统计分析和改进运营，将已经去标识化无法识别您身份且不能复原的信息用于建立数据库并进行商业化利用。例如通过您的偏好等进行统计分析，从而改进我们的产品、服务或营销计划；又如为改进我们系统而进行的技术改造、网络维护、故障排除、内部政策与流程制定、生成内部报告等。<br/>
 
二、我们如何使用Cookie和同类技术<br/>
（一）Cookie的使用<br/>
为确保网站/程序正常高效运转、为您获得更轻松的访问体验、向您推荐您可能感兴趣的内容，我们会在您的设备终端/系统上存储名为 Cookie的小数据文件。Cookie会帮助您在后续访问我们网站时调用您的信息，简化您填写个人信息(例如一键登录等)的流程;为您提供安全购物的偏好设置;帮助您优化对广告的选择与互动;保护您的数据安全等。我们不会将 Cookie用于本隐私政策所述目的之外的任何用途。您可根据自己的偏好管理或删除 Cookie。您可以清除计算机或移动设备上保存的所有 Cookie，您有权接受或拒绝Cookie。大多数浏览器会自动接受Cookie，但您通常可根据自己的需要来修改浏览器的设置以拒绝Cookie;另外，您也可以清除软件内保存的所有Cookie。但您可能因此无法完全体验我们某些便捷性和安全性的服务功能。<br/>
 
（二）网络Beacon和同类技术的使用<br/>
除Cookie外，我们网页上常会包含一些电子图象(称为"单像素"GIF文件或"网络Beacon")等其他同类技术，它们可以帮助网站计算浏览网页的用户或访问某些Cookie。我们使用网络Beacon的方式有:<br/>
1、我们通过在我们网站上使用网络Beacon，计算用户访问数量，并通过访问Cookie辨认注册用户。<br/>
2、我们通过得到的Cookie信息，可以在我们网站提供个性化服务。<br/>
 
三、我们如何共享、转让、公开披露您的个人信息<br/>
（一）共享<br/>
我们不会与关联公司以外的任何公司、组织和个人共享您的个人信息，但以下情况除外：<br/>
1、获得您明确同意或授权的共享。<br/>
2、基于法定情形下：根据法律法规的规定、诉讼争议解决需要，或行政、司法等有权机关依法提出的要求。<br/>
3、与关联公司共享：为向您提供一致化服务以及便于您进行统一管理，我们可能会将您的个人信息与我们的关联公司共享。但我们只会共享必要的个人信息，如果我们共享您的个人敏感信息或者关联方改变个人信息的使用目的，将再次征求您的授权同意。<br/>
4、与合作伙伴分享：我们可能会向业务合作伙伴共享为您提供服务所必要的订单信息等。<br/>
5、基于合理商业习惯：例如与第三方共享联合营销活动中的中奖信息，以便第三方能及时向您发放奖品。<br/>
6、基于学术研究；例如为科研机构开展统计或学术研究之必要。<br/>
7、基于符合法律法规的社会公共利益等。<br/>
我们会通过应用程序接口（API）、软件工具开发包（SDK）与第三方进行必要的数据共享，不同版本的第三方SDK会有所不同，一般包括第三方账号登录类、分享类、第三方支付类、地图导航类、厂商推送类、统计类等，我们会对第三方进行严格的安全检测并约定数据保护措施。<br/>
请您知悉，我们仅会出于合法、正当、必要、特定、明确的目的共享您的个人信息，对我们仅为实现本政策中声明的目的与之共享个人信息的公司、组织和个人，我们会与其签署严格的信息保护和保密协定，要求他们遵守协议并采取相关的安全措施来保护您的个人信息。<br/>
 
（二）转让<br/>
随着我们业务的发展，我们及我们的关联方有可能进行合并、收购、资产转让或类似的交易，如涉及个人信息的转让，我们会要求受让您个人信息的公司、组织继续接受本隐私政策的约束，否则,我们将要求该公司、组织重新征求您的授权同意。<br/>
 
（三）公开披露<br/>
我们仅会在以下情况下，且采取符合业界标准的安全防护措施的前提下，才可能公开披露您的个人信息：<br/>
1、根据您的需求，在您明确同意的披露方式下披露您所指定的个人信息；<br/>
2、根据法律、法规的要求、强制性的行政执法或司法要求所必须提供您个人信息的情况下，我们可能会依据所要求的个人信息类型和披露方式公开披露您的个人信息。在符合法律法规的前提下，当我们收到上述披露信息的请求时，我们会要求必须出具与之相应的法律文件，如传票或调查函。<br/>
请注意，您在使用我们服务时自愿发布甚至公开分享的信息，可能会涉及您或他人的个人信息甚至个人敏感信息，如您的交易信息，以及您在评价时选择上传包含个人信息的文字、图片或视频等各种形式的信息。请您在使用我们的服务时更加谨慎地考虑，是否要发布甚至公开分享相关信息。<br/>
 
（四）共享、转让、公开披露个人信息时事先征得授权同意的例外<br/>
以下情形中，共享、转让、公开披露您的个人信息无需事先征得您的授权同意：<br/>
1、与国家安全、国防安全有关的；<br/>
2、与公共安全、公共卫生、重大公共利益有关的；<br/>
3、与犯罪侦查、起诉、审判和判决执行等有关的；<br/>
4、出于维护您或其他个人的生命、财产等重大合法权益但又很难得到本人同意的；<br/>
5、其他维护公共利益的情形，例如您的信用评价信息需要被公开/共享；<br/>
6、您自行向社会公众公开的个人信息；<br/>
7、从合法公开披露的信息中收集个人信息的，如合法的新闻报道、政府信息公开等渠道。<br/>
根据法律规定，共享、转让、公开披露经去标识化处理的个人信息，且确保数据接收方无法复原并重新识别个人信息主体的，我们对此类数据的处理将无需另行向您通知并征得您的同意。<br/>
 
四、我们如何保存和保护您的个人信息<br/>
（一）个人信息的保存<br/>
1、保存期限：除非依据法律法规或双方约定，我们仅会在实现目的所必需的最短时间内留存您的相关个人信息。在您主动注销账号时，我们将根据法律法规的要求尽快删除您的个人信息或匿名化处理，有关注销账号的相关规则和流程，请参见本政策附件中的《用户注销协议》。<br/>
2、保存地域：我们在中华人民共和国境内收集和产生的个人信息，将存储在中国境内，但以下情形除外：<br/>
法律法规有明确规定的；<br/>
单独征得您的授权同意；<br/>
您主动发起的跨境预定、下单、交易等个人行为（如购买国际机票、预订国际酒店等）。<br/>
在上述情形中，我们会并要求数据接收方按照本隐私政策以及其他相关的安全保密措施来处理个人信息。<br/>
3、终止运营：如果发生终止运营等情形，我们将会至少提前30天通知您，并在终止运营后对您的个人信息进行删除或匿名化处理。<br/>
 
（二）个人信息的保护措施<br/>
1、数据安全措施<br/>
为保障您的信息安全，我们努力采取各种符合业界标准的物理、电子和管理方面的安全措施来保护您的个人信息，建立数据分类分级制度、数据安全管理规范、数据安全开发规范来管理规范个人信息的存储和使用。通过信息接触者保密协议、监控和审计机制来对数据进行全面安全控制。防止您的个人信息遭到未经授权访问、公开披露、使用、修改、损坏或丢失。<br/>
2、请您知悉并理解，互联网并非绝对安全的环境，我们强烈建议您通过安全方式、使用复杂密码，协助我们保证您的账号安全。如您发现自己的个人信息泄密，尤其是您的账户或密码发生泄露，请您立即根据本隐私政策中提供的联系方式联络我们，以便我们采取相应措施。<br/>
3、安全事件<br/>
在不幸发生个人信息安全事件后，我们会立即成立专项应急小组，启动应急预案，防止安全事件扩大，并按照法律法规的要求及时向您告知:安全事件的基本情况和可能的影响、我们已采取或将要采取的处置措施、您可自主防范和降低风险的建议、对您的补救措施等。我们将及时将事件相关情况以邮件、信函、电话、推送通知等方式告知您，难以逐一告知个人信息主体时，我们会采取合理、有效的方式发布公告。同时，我们还将按照监管部门要求，主动上报个人信息安全事件的处置情况。<br/>
 
五、您如何管理您的个人信息<br/>
您有权访问、更正、删除您的个人信息，法律法规规定的例外情况除外。您可以通过以下方式管理您的信息:<br/>
1、更正、更新和删除您的注册账户；<br/>
2、选择或变更宁德订阅、新闻和通知的个人定制；<br/>
3、选择是否接受有关我们的产品和服务或我们认为您可能感兴趣的产品和服务的促销优惠信息。<br/>
4、请求从我们的某个网站或应用程序的公共论坛删除您的个人信息。<br/>
5、请求访问我们所掌握的关于您的个人信息以及他们进行修改或删除。<br/>
如果您无法通过上述链接管理这些个人信息，您可以随时通过本隐私政策中提供的反馈方式联系我们。我们将在15天内回复您的访问请求。<br/>
  
六、未成年人的个人信息保护<br/>
我们非常重视对未成年人个人信息的保护。我们的网站和服务主要面向成人。如您为未成年人的，建议您请您的父母或监护人仔细阅读本隐私权政策，并在征得您的父母或监护人同意的前提下使用我们的服务或向我们提供信息。<br/>
对于经父母或监护人同意使用我们的产品或服务而收集未成年人个人信息的情况，我们只会在法律法规允许、父母或监护人明确同意或者保护未成年人所必要的情况下使用、共享、转让或披露此信息。<br/>
如果我们发现自己在未事先获得可证实的父母或法定监护人同意的情况下收集了未成年人的个人信息，则会设法尽快删除相关数据。<br/>
 
七、通知和修订<br/>
为给您提供更好的服务，我们的业务将不时变化，本隐私政策也将随之调整。未经您明确同意，我们不会削减您依据本隐私政策所应享有的权利。我们会通过在我们网站、移动端上发出更新版本或以其他方式提醒您相关内容的更新，也请您访问我们以便及时了解最新的隐私政策。在前述情况下，若您继续使用我们的服务，即表示同意接受修订后的本政策并受之约束。<br/>
 
八、如何联系我们<br/>
如果您对本隐私政策有意见或问题，请联系客户服务部。 <br/>

      `
    };
  }
};
</script>
