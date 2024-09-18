<template>
  <div class="hello">
    <!--    <h1>{{ msg }}</h1>-->
    <h1>学习Vue3：模板语法</h1>
    <p>{{ msg }}</p>
    <div>{{ rawHtml }}</div>
    <div v-html="rawHtml"></div>
    <div v-bind:id="dynamicId"></div>
    <p>{{ num + 10 }}</p>
    <p>{{ isFlag ? "孙猴子" : "假猴子" }}</p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      msg: "测试",
      rawHtml: "<span style=\"color:red\">这个应该是红色的.</span>",  //动态渲染HTML
      dynamicId: 1001,                                            //动态绑定属性
      num: 10, //计算属性
      isFlag: true, //三元表达式
    }
  }
}
</script>
