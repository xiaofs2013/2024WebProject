<template>
  <div class="hello">
    <!-- v-model 双向数据绑定 在数据发生改变时，渲染的数据也同时发生改变   -->
    <!-- v-model="userName" 会自动绑定到data中的userName -->
    <!--  修饰符: trim 忽略空格 -->
    <!--  修饰符：.lazy 将同步转换为非同步，也就是在change事件后，再进行同步 -->
    <input type="text" v-model.trim="userName">
    <br>
    <input type="text" v-model.trim="passWord">
    <p>{{ userName }}<span v-if="userName && passWord">,</span>{{ passWord }}</p>
    <button @click="clickUserName">获取用户名</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      count: 1,
      userName: "",
      passWord: ""
    }
  },

  // 事件处理函数 跟data同级
  methods: {
    clickUserName() {
      alert(this.userName + " " + this.passWord);
    }
  }


}
</script>