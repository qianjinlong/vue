<template>
  <div class="login_account_view">
    <div
      id="login"
      class="loginbyaccount"
      @click="LoginVali"
    >登录</div>
    <!-- 58 -->
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

    <div class="error"><span id="loginname_error">{{ loginname_errordata}}</span></div>
    <div :class="[loginname_view, loginnameBorderColor]">
      <span class="icon-loginname"></span>
      <input
        id="loginname"
        class="loginname"
        type="text"
        placeholder="登录名"
        v-model="loginname"
        @focus="LoginNameValiFocus"
        @blur="LoginNameValiBlur"
      />
    </div>
    <div class="error"><span id="institution_error">{{ institution_errordata }}</span></div>
    <div :class="[institution_view, institutionBorderColor]">
      <span class="icon-institution"></span>
      <input
        id="institution"
        class="institution"
        type="text"
        placeholder="请输入机构后缀"
        v-model="institution"
        @focus="InstitutionValiFocus"
        @blur="InstitutionValiBlur"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: 'LoginByAccount',
  data () {
    return {
      institution: '',
      loginname: '',//
      password: '',
      institution_errordata: '',
      loginname_errordata: '',
      password_errordata: '',
      institution_view: 'institution_view',
      institutionBorderColor: 'borderColor1',
      loginname_view: 'loginname_view',
      loginnameBorderColor: 'borderColor1',
      password_view: 'password_view',
      passwordBorderColor: 'borderColor1'
    }
  },
  methods: {
    InstitutionValiFocus () {
      this.institution_errordata = ''
      this.institutionBorderColor = 'borderColor2'
    },
    InstitutionValiBlur () {
      this.institutionBorderColor = 'borderColor1'
    },
    LoginNameValiFocus () {
      this.loginname_errordata = ''
      this.loginnameBorderColor = 'borderColor2'
    },
    LoginNameValiBlur () {
      this.loginnameBorderColor = 'borderColor1'
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
      if (this.institution.trim() === '') {
        this.institution_errordata = '请输入机构后缀'
        this.institutionBorderColor = 'borderColor3'
        flag = false
      }
      if (this.loginname.trim() === '') {
        this.loginname_errordata = '请输入用户名'
        this.loginnameBorderColor = 'borderColor3'
        flag = false
      }
      if (this.password.trim() === '') {
        this.password_errordata = '请输入密码'
        this.passwordBorderColor = 'borderColor3'
        flag = false
      }
      if (flag) {
        alert('机构后缀：' + this.institution + '，用户名：' + this.loginname + '，密码：' + this.password)
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

.loginame_view,
.institution_view,
.password_view {
  margin: 0 auto;
  width: 372px;
  padding-bottom: 10px;
  display: flex;
  justify-content: space-between;
}
.loginame_view,
.password_view {
  margin-top: 35px;
}

.icon-institution,
.icon-password,
.icon-loginname {
  display: block;
  width: 32px;
  height: 32px;
  background-repeat: no-repeat;
  background-size: 20px auto;
  background-position: 0px 5px;
}

.icon-institution {
  background-image: url(https://cdn.schoolpal.cn/schoolpal/resource/ci/SchoolPal-NETCore-PC/130/common/images/login/enameaccount.svg);
}

.icon-password {
  background-image: url(https://cdn.schoolpal.cn/schoolpal/resource/ci/SchoolPal-NETCore-PC/130/common/images/login/password.svg);
}

.icon-loginname {
  background-image: url(https://cdn.schoolpal.cn/schoolpal/resource/ci/SchoolPal-NETCore-PC/130/common/images/login/usernameaccount.svg);
}

.institution,
.loginname,
.password {
  width: 340px;
  height: 24px;
  font-size: 14px;
  border: none;
  outline: none;
}

.loginbyaccount {
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
  margin-top: 57px;
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
