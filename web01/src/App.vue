<template>
  <div id="app">
    <Header></Header>
    <List :todos="todos"></List>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import List from './components/List.vue'
export default {
  name: 'App',
  data() {
    return {
      todos:[
        {id:"001",title:"周四核酸",done:false},
        {id:"002",title:"英语作业",done:true},
        {id:"003",title:"Vue实验",done:false}
      ]
    }
  },
  components: {
    Header,
    Footer,
    List
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
  width: 600px;
}
</style>
