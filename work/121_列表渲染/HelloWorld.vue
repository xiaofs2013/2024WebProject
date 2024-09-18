<template>
  <div class="hello">
    <h3>列表渲染</h3>
    <ul>
<!--   唯一ID很重要，会用来比对数据来决策是否刷新     -->
      <li v-for="item in newList" v-bind:key="item.id">{{ item.title }}</li>
<!--    如果数据没有ID 那么可以通过下标来替代 但唯一索引ID很重要的  -->
<!--      <li v-for="(item, index) in newList" v-bind:key="index">{{ item.title }}</li>-->
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      newList: [
        {id: 10001, title: "今日新闻1"},
        {id: 10002, title: "今日新闻2"},
        {id: 10003, title: "今日新闻3"},
          //就地策略 不会重新渲染数据 只会渲染新添加的数据一次 优化了性能
          //前面的数据都不会动
        {id: 10004, title: "今日新闻4"}
      ]
    }
  }
}
</script>