<template>
  <div class="lv">
    <top />
    <div class="main">
      <div class="main_inner">
        <div class="main_inner_row1">
          <div class="adv"></div>
          <div
            class="login_view"
            v-show="tabId === 0"
          >
            <LoginByTelphone />
            <div class="login_top">
              <span class="login_telphone">
                <span
                  class="login_title"
                  @click="tabId=0"
                >手机号码登录</span>
                <span class="login_logo_blue"></span>
              </span>
              <span class="login_telphone">
                <span
                  class="login_title"
                  @click="tabId=1"
                >账号登录</span>
                <span class="login_logo_blue"></span>
              </span>
            </div>
          </div>

          <div
            class="login_view"
            v-show="tabId === 1"
          >
            <LoginByAccount />
            <div class="login_top">
              <span class="login_telphone">
                <span
                  class="login_title"
                  @click="tabId=0"
                >手机号码登录</span>
                <span class="login_logo_blue"></span>
              </span>
              <span class="login_telphone">
                <span
                  class="login_title"
                  @click="tabId=1"
                >账号登录</span>
                <span class="login_logo_blue"></span>
              </span>
            </div>
          </div>
        </div>

        <div class="main_inner_row2">
          <div class="item">
            <span>相关产品</span>

            <div class="product">

              <div class="product_item">
                <div>
                  <img src="https://prox.schoolpal.cn/common/images/icon-scp.png" />
                  <div>
                    <span>校宝收银宝</span>
                    <span>学校收费标准</span>
                  </div>
                </div>
              </div>

              <div class="product_item">
                <div>
                  <img src="https://prox.schoolpal.cn/common/images/icon-zhaoshengbao.png" />
                  <div>
                    <span>校宝招生宝</span>
                    <span>一站招生服务</span>
                  </div>
                </div>
              </div>

              <div class="product_item">
                <div>
                  <img src="https://prox.schoolpal.cn/common/images/icon-anxinbao.png" />
                  <div>
                    <span>校宝安心宝</span>
                    <span>教育保险精选</span>
                  </div>
                </div>
              </div>

            </div>

          </div>

          <div class="item">
            <span>咨询热线</span>
            <span>400-6999-707</span>
          </div>

        </div>
      </div>
    </div>
  </div>
</template>

<script>
import LoginTop from '@/components/LoginTop'
import LoginByTelphone from '@/components/LoginByTelphone'
import LoginByAccount from '@/components/LoginByAccount'
export default {
  name: 'Login',
  data () {
    return {
      tabId: 0
    }
  },
  components: {
    top: LoginTop,
    LoginByTelphone: LoginByTelphone,
    LoginByAccount: LoginByAccount
  }
}
</script>
<style>
.lv {
  height: 100%;
}

.borderColor1 {
  border-bottom: 1px #f0f0f0 solid;
}

.borderColor2 {
  border-bottom: 1px #007aff solid;
}

.borderColor3 {
  border-bottom: 1px #f36 solid;
}

.login_telphone {
  display: block;
  width: 50%;
}

.login_top {
  display: flex;
  justify-content: space-between;
}

.main {
  height: 100%;
  background-color: #f2f6fc;
  display: flex;
  justify-content: center;
  align-items: center;
}

.main_inner {
  width: 1000px;
}

.main_inner_row1 {
  height: 510px;
  border-radius: 8px;
  overflow: hidden;
  display: flex;
  justify-content: space-between;
}

.main_inner_row1 .adv {
  width: 560px;
  background-image: url(https://schoolpal.oss-cn-hangzhou.aliyuncs.com/erpbanner/erplogin0827.jpg);
  background-repeat: no-repeat;
  background-size: 560px 510px;
}

.login_view {
  /* .main_inner_row1 */
  width: 440px;
  background-color: #fff;
  padding-bottom: 30px;
  display: flex;
  flex-direction: column-reverse;
}

.login_title {
  width: 60%;
  margin: 0 auto;
  display: block;
  font-size: 18px;
  font-weight: bold;
  text-align: center;
}

.login_title:hover {
  cursor: pointer;
}

.login_logo_blue {
  display: block;
  width: 32px;
  height: 5px;
  margin: 0 auto;
  margin-top: 10px;
  margin-bottom: 40px;
  border-radius: 4px;
  background-color: #007aff;
}

.account_view,
.password_view {
  margin: 0 auto;
  width: 372px;
  padding-bottom: 10px;
  display: flex;
  justify-content: space-between;
}

.password_view {
  margin-top: 35px;
}

.icon-account,
.icon-password {
  display: block;
  width: 32px;
  height: 32px;
  background-repeat: no-repeat;
  background-size: 20px auto;
  background-position: 0px 5px;
}

.icon-account {
  background-image: url(https://cdn.schoolpal.cn/schoolpal/resource/ci/SchoolPal-NETCore-PC/130/common/images/login/telaccount.svg);
}

.icon-password {
  background-image: url(https://cdn.schoolpal.cn/schoolpal/resource/ci/SchoolPal-NETCore-PC/130/common/images/login/password.svg);
}

.account,
.password {
  width: 340px;
  height: 24px;
  font-size: 14px;
  border: none;
  outline: none;
}

.login {
  width: 320px;
  height: 54px;
  font-size: 16px;
  font-weight: bold;
  color: #fff;
  text-align: center;
  line-height: 54px;
  background-color: #007aff;
  border-radius: 50px;
  margin: 0 auto;
  margin-top: 150px;
}

.main_inner_row2 {
  margin-top: 10px;
  display: flex;
  justify-content: space-between;
}

.item > span {
  display: block;
  font-size: 16px;
  font-weight: bold;
  margin-bottom: 10px;
}

.product {
  display: flex;
  flex-direction: row;
}

.product div {
  width: 210px;
  height: 60px;
  margin-right: 10px;

  border-radius: 10px;
  display: flex;
  flex-direction: row;
  justify-content: center;
}

.product_item img {
  width: 40px;
  height: 40px;
  margin-top: 10px;
}

.product_item > div div {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.product_item div {
  width: 140px;
  margin: 0 auto;
}

.product_item span {
  display: block;
  font-weight: bold;
}

.product_item span:nth-child(1) {
  font-size: 14px;
}

.product_item span:nth-child(2) {
  font-size: 12px;
}

.item:last-child span:last-child {
  font-size: 28px;
  padding-top: 10px;
  padding-right: 10px;
}

.error {
  width: 100%;
  display: flex;
  flex-direction: row-reverse;
  height: 15px;
}

.error span {
  display: block;
  color: #f36;
  font-size: 12px;
  padding-right: 35px;
}

#login:hover {
  background-color: #0064dc;
  cursor: pointer;
}

.product_item:hover {
  background-color: rgb(245, 203, 207);
  cursor: pointer;
}
</style>
