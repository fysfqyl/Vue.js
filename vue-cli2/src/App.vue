<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <BlogItem title="微博标题1" time="2022-4-1" content="内容11"/>
    <BlogItem title="微博标题2" time="2022-4-2" content="内容1122"/>
    <h2>动态参数传递</h2>
    <BlogItem :title="blog.title" :time="blog.time" :content="blog.content"/>
    <h2>动态参数+循环</h2>
    <BlogItem v-for="(item,index) in blogs" :key="index" :title="item.title" :time="item.time" :content="item.content"/>
  </div>
</template>

<script>
import BlogItem from './components/BlogItem.vue'

export default {
  name: 'App',
  data() {
    return{
      blog:{title:"微博标题1",time:"2022-4-1",content:"单对象数据"},
      blogs:[
        {title:"微博标题1",time:"2022-4-4",content:"多对象数据1"},
        {title:"微博标题2",time:"2022-4-5",content:"多对象数据2"},
        {title:"微博标题3",time:"2022-4-6",content:"多对象数据3"}
      ]
    }
  },
  components: {
    BlogItem
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
