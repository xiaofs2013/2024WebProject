<template>

  <h3>prop传递数据</h3>
  <p>{{ title }}</p>
  <p>{{ myValue }}</p>
  <p>age = {{ age }}</p>
  <ul>
    <li v-for="(item,index) in names" v-bind:key="index">{{ item }}</li>
  </ul>

</template>


<script>
export default {
  name: "MyComponent",
  props: {   // 定义props属性  props代表接收父组件传递过来的数据
             // title、myValue、age是父组件传递过来的数据
             //prop传递的参数是没有类型限制的
             //包括对象类型、数组类型、函数类型（方法也能传来调用）等等
            //prop不能进行反向传递（子类传父类） 但可以通过自定义事件进行传递
    title: {
      type: String,
      default: ""
    },
    myValue: {
      type: String,
      default: ""
    },
    age: {
      type: Number,
      default: 0
    },
    names: {
      type: Array,
      //数组和对象必须用函数进行返回
      default: function () {
        return [];
      }
    }
  }
} 
</script>

<style scoped>

</style>