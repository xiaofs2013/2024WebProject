<template>
  <div class="hello">
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      count: 1
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