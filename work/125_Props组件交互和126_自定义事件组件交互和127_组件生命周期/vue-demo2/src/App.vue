<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <my-component v-bind:title="title" v-bind:myValue="myValue" v-bind:age="age"
                v-bind:names="names"
  /> <!-- 使用组件 -->

  <!--  自定义事件传递数据-->
  <my-component-for-parent @onEvent="getDataHandle"/>
  <p>{{ message }}</p>


  <!--  生命周期-->
  <my-component-for-life/>

</template>

<script>
import myComponent from "@/components/MyComponent.vue"; // 引入组件
import myComponentForParent from "@/components/MyComponentForParent.vue";
import myComponentForLife from "@/components/MyComponentForLife.vue";
import MyComponentForLife from "@/components/MyComponentForLife.vue";

export default {
  name: 'App',
  data() {
    return {
      title: "我是一个标题",
      myValue: "我是一个值",
      age: 18,
      names: ["张三", "李四", "王五"],
      message: null,
    }
  },
  components: {
    MyComponentForLife,
    myComponent, // 注册组件
    myComponentForParent,
    myComponentForLife,
  },
  methods: {
    getDataHandle(data) {
      //如果页面P标签中显示有数据，再次点击则清空
      if (this.message) {
        this.message = "";
      } else {
        this.message = data;
      }
    }
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
