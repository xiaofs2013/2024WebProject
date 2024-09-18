<template>
  <div class="hello">
    <button v-on:click="count += 1">点击:{{ count }}</button>
    <button v-on:click="handle">按钮</button>
    <p>{{ message }}</p>
    <button v-on:click="say('hi')">say(hi)</button>
    <button v-on:click="say('what')">say(what)</button>
    <ul>
      <!--  每个标签添加事件    -->
      <li v-on:click="printData(item,$event)" v-for="(item,index) in names" v-bind:key="index">{{ item }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      count: 1,
      message: 'hello world',
      names: ['tom', 'jerry', 'kitty']
    }
  },

  // 事件处理函数 跟data同级
  methods: {
    handle(event) {
      //在事件中，如果需要读取data中的数据，是需要通过this来进行读取的
      if (this.message === 'hello world') {
        this.message = 'hello vue'
      } else {
        this.message = 'hello world'
      }
      //标签中的方法如果需要传递参数（方法后面有括号），可以通过$event来传递,如handle(value, $event)
      console.log(event);// 这里的 event 是 Vue 自动传递的
      let innerText = event.target.innerText;
      if (innerText === '按钮') {
        event.target.innerText = '我被点击了'
      } else {
        event.target.innerText = '按钮'
      }
    },

    say(data) {
      alert(data);
    },

    //如果强校验，event会在没有使用时报错
    //单纯的事件处理函数，不需要传递参数，可以省略event
    printData(item, event) {
      let innerText = event.target.innerText;
      console.log(innerText);
      alert(item);
    },

  }


}
</script>