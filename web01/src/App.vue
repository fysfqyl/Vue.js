<template>
  <div id="app">
    <Header :add="add"/>
    <List :todos="todos" :delTodo="delTodo"></List>
    <Footer :todos="todos" :checkAll="checkAll" :clearAll="clearAll"></Footer>
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
  methods: {
    add(obj){
      this.todos.push(obj)
    },
    delTodo(id) {
      this.todos=this.todos.filter(todo=>todo.id!=id)
    },
    checkAll(done) {
      this.todos.forEach(todo=>{
        todo.done=done
      })
    },
    clearAll() {
      this.todos=this.todos.filter(todo=>todo.done===false)
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
.btn {
  display: inline-block;
  padding: 4px 12px;
  margin-bottom: 0;
  font-size: 14px;
  line-height: 20px;
  text-align: center;
  vertical-align: middle;
  cursor: pointer;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.2), 0 1px 2px rgba(0, 0, 0, 0.05);
  border-radius: 4px;
}

.btn-danger {
  color: #fff;
  background-color: #da4f49;
  border: 1px solid #bd362f;
}

.btn-danger:hover {
  color: #fff;
  background-color: #bd362f;
}

.btn:focus {
  outline: none;
}
</style>
