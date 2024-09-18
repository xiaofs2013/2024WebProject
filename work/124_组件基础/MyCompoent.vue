<!--HTML方法块-->
<template>
  <h3>我是单文件组件</h3>
</template>

<!--JS方法块-->
<script>
export default {
  name: "MyCompoent"   //组件名
}
</script>

<!--CSS方法块-->
<!--scoped如果添加该子属性 就代表当前样式只在当前组件中生效-->
<style scoped>

h3 {
  color: red;
}

</style>