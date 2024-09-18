<template>
  <h3>生命周期函数</h3>
  <p>{{ message }}</p>
<!-- 点击以后数据更新 调用beforeUpdate和update -->
  <button @click="message='数据'">点击</button>
</template>

<script>
export default {
  name: "MyComponentForLife",
  data() {
    return {
      message: ''
    }
  },

  // 生命周期函数
  //生命周期的执行顺序：beforeCreate -> created -> beforeMount -> mounted -> beforeUpdate -> updated -> beforeUnmount -> unmounted
  //哪怕打乱顺序，也是按照这个顺序执行
  //生命周期函数的作用：在某个时间点执行某个操作
  //频率使用中最高的生命周期函数：created
  beforeCreate() {
    console.log('beforeCreate组件创建之前');
  },
  //使用频率最高
  created() {
    console.log('created组件创建完成');
    //在页面打开的时候，就将数据渲染上去
    //打开后就有数据
  },
  beforeMount() {
    console.log('beforeMount组件挂载（渲染）之前');
  },
  mounted() {
    console.log('mounted组件挂载（渲染）完成');
    //可能会将网络请求放在这里
    //就是先出现页面 再将数据渲染上去
  },
  beforeUpdate() {
    console.log('beforeUpdate组件更新之前');
  },
  updated() {
    console.log('updated组件更新完成');
  },
  beforeUnmount() {
    console.log('beforeUnmount组件卸载之前');
    //卸载之前，将消耗性能的都干掉
    //比如定时器
  },
  unmounted() {
    console.log('unmounted组件销毁完成');
  }
}
</script>

<style scoped>

</style>