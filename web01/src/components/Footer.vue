<template>
<div>
    <div class="todo-footer">
        <label>
          <input type="checkbox" v-model="isAll"/>
        </label>
        <span>
          <span>已完成{{finished}}</span> / 全部{{all}}
        </span>
        <button class="btn btn-danger" @click="clearAll">清除已完成任务</button>
      </div>
</div>
</template>

<script>
export default {
  props:["todos","checkAll","clearAll"],
  // 计算属性
  computed:{
    all() {
      return this.todos.length
    },
    finished() {
      return this.todos.filter(todo=>todo.done===true).length
    },
    // isAll(){
    //   return this.all === this.finished
    // }
    isAll:{
      get() {
        // 这是得到的值true or false
        return this.all === this.finished
      },
      set(value) {
        // value这里代表上面get到的true or false，将其作为done传给APP.vue的checkAll(done)
        this.checkAll(value)
      }
    }
  }
}

</script>

<style>
/*footer*/
.todo-footer {
  height: 40px;
  line-height: 40px;
  padding-left: 6px;
  margin-top: 5px;
}

.todo-footer label {
  display: inline-block;
  margin-right: 20px;
  cursor: pointer;
}

.todo-footer label input {
  position: relative;
  top: -1px;
  vertical-align: middle;
  margin-right: 5px;
}

.todo-footer button {
  float: right;
  margin-top: 5px;
}
</style>