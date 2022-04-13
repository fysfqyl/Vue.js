<template>
  <div>
    <ul class="todo-main">
      <Item v-for="(todo,index) in todos" :key="index" :todo="todo" :delTodo="delTodo"/>
    </ul>
  </div>
</template>

<script>
import Item from "./Item.vue"
export default {
    props:["todos","delTodo"],
    components:{
      Item
    }
}

</script>

<style>

</style>