<template>
<div>
    
        <li @mouseover="show=true" @mouseleave="show=false">
          <label>
            <input type="checkbox" v-model="todo.done"/>
            <span>{{todo.title}}</span>
          </label>
          <button class="btn btn-danger" v-show="show" @click="delTodo(todo.id)">删除</button>
        </li>
    
</div>
</template>

<script>
export default {
    props:["todo","delTodo"],
    data() {
        return {
            show:false
        }
    },
}

</script>

<style>
li {
  list-style: none;
  height: 36px;
  line-height: 36px;
  padding: 0 5px;
  border-bottom: 1px solid #ddd;
}

li label {
  float: left;
  cursor: pointer;
}

li label li input {
  vertical-align: middle;
  margin-right: 6px;
  position: relative;
  top: -1px;
}

li button {
  float: right;
  display: none;
  margin-top: 3px;
}

li:before {
  content: initial;
}

li:last-child {
  border-bottom: none;
}
</style>