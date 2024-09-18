<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
<!-- 第三步 使用组件  -->
  <MyCompoent></MyCompoent>
</template>

<script>

import MyCompoent  from "./MyCompoent.vue"; //第一步引入组件

export default {
  name: 'App',
  components: {  //第二步 注册组件 或 挂载组件
    MyCompoent

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
