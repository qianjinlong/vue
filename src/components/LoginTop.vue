<template>
  <div>
    <div class="top">
      <div class="top_inner">
        <div class="top_logo"></div>
        <div class="top_nav">
          <div><span>公众号</span></div>
          <div><span>帮助</span></div>
          <div><span>周边</span></div>
          <div><span>官网</span></div>
          <div><span>申请使用</span></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LoginTop'
}
</script>

<style>
.top {
  background-color: #fff;
}

.top_inner {
  width: 1000px;
  height: 60px;
  line-height: 60px;
  font-size: 16px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
}

.top_logo {
  width: 180px;
  background-image: url(https://cdn.schoolpal.cn/schoolpal/resource/ci/SchoolPal-NETCore-PC/130/common/images/icon-loginlogo-new.jpg?version=20201022223932);
  background-repeat: no-repeat;
  background-size: contain;
  background-position: 0;
}

.top_nav {
  display: flex;
  flex-direction: row-reverse;
}

.top_nav div {
  width: 80px;
  text-align: center;
}

.top_nav div span {
  display: block;
  width: 65px;
}

.top_nav div span:hover {
  cursor: pointer;
  border-bottom: 2px #007aff solid;
}
</style>
