// 这是vue插件的父元素，各个组件的集合，在此处引入组件，注册、使用
<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <MyStudent></MyStudent>
  </div>
</template>

<script>
import MyStudent from './components/MyStudent.vue'

export default {
  name: 'App',
  // 注册组件
  components: {
    MyStudent
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
