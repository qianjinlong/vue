<template>
  <div class="login_account_view">
    <div
      id="login"
      class="loginbytelphone"
      @click="LoginVali"
    >登录</div>
    <div class="error"><span id="password_error">{{password_errordata}}</span></div>
    <div :class="[password_view, passwordBorderColor]">
      <span class="icon-password"></span>
      <input
        id="password"
        class="password"
        type="password"
        placeholder="请输入密码"
        v-model="password"
        @focus="PasswordValiFocus"
        @blur="PasswordValiBlur"
      />
    </div>
    <div class="error"><span id="account_error">{{ account_errordata }}</span></div>
    <div :class="[account_view, accountBorderColor]">
      <span class="icon-account"></span>
      <input
        id="account"
        class="account"
        type="text"
        placeholder="请输入手机号码"
        v-model="account"
        @focus="AccountValiFocus"
        @blur="AccountValiBlur"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: 'LoginByTelphone',
  data () {
    return {
      account: '',
      password: '',
      account_errordata: '',
      password_errordata: '',
      account_view: 'account_view',
      accountBorderColor: 'borderColor1',
      password_view: 'password_view',
      passwordBorderColor: 'borderColor1'
    }
  },
  methods: {
    AccountValiFocus () {
      this.account_errordata = ''
      this.accountBorderColor = 'borderColor2'
    },
    AccountValiBlur () {
      if (this.account.length === 0 || this.account.length === 11) {
        this.account_errordata = ''
        this.accountBorderColor = 'borderColor1'
      } else {
        this.account_errordata = '请输入正确的手机号'
        this.accountBorderColor = 'borderColor3'
      }
    },
    PasswordValiFocus () {
      this.password_errordata = ''
      this.passwordBorderColor = 'borderColor2'
    },
    PasswordValiBlur () {
      this.passwordBorderColor = 'borderColor1'
    },
    LoginVali () {
      var flag = true
      if (this.account.trim().length !== 11) {
        this.account_errordata = '请输入正确的手机号'
        this.accountBorderColor = 'borderColor3'
        flag = false
      }
      if (this.password.trim() === '') {
        this.password_errordata = '请输入密码'
        this.passwordBorderColor = 'borderColor3'
        flag = false
      }
      
      if (flag) {
        alert('手机号：' + this.account + '，密码：' + this.password)
      }
      return false
    }
  }
}
</script>

<style>
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

.login_account_view {
  /* .main_inner_row1 */
  width: 440px;
  background-color: #fff;
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
.loginname_view,
.password_view {
  margin: 0 auto;
  width: 372px;
  padding-bottom: 10px;
  display: flex;
  justify-content: space-between;
}

.password_view,
.loginname_view {
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

.loginbytelphone {
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
