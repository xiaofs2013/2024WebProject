<template>

  <h3>自定义数据传递事件</h3>
  <button @click="dataTransmission">点击传递</button>

</template>


<script>
export default {
  name: "MyComponentForParent",
  props: {},
  data() {
    return {
      messageValue: "我是MyComponentForParent的数据",
    }
  },


  methods: {
    dataTransmission() {
      //触发自定义事件
      //参数1：字符串（理论上是随便写的，但需要具有意义） 参数2：传递的数据
      //字符串就是自定义事件的名称
      //比如@click、@change是Vue内置的事件
      //调用你的方法，传递数据 就是@onEvent
      this.$emit("onEvent", this.messageValue);
    }
  }

}
</script>

<style scoped>

</style>