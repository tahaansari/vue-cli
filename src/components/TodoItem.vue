<template>
  <div>
      <div class="todo-item" :class="{'isCompleted':todo.completed}">
        <input type="checkbox" @change="toggleCompleted">
        {{todo.title}}
        <button class="del" @click="$emit('del-todo',todo.id)">X</button>
      </div>
  </div>
</template>

<script>
export default {
  name:"TodoItem",
  data(){
    return{
      todoitem:this.todo
    }
  },
  props:['todo'],
  methods:{
    toggleCompleted(){
      this.todoitem.completed = !this.todoitem.completed;
    }
  }
}
</script>

<style scoped>
.todo-item{
  background-color: aliceblue;
  padding: 10px 20px;
  border-top: 1px solid black;
  border-bottom: 1px solid rgb(221, 221, 221);
}
.todo-item.isCompleted{
  text-decoration: line-through;
}
.del{
  display: inline-block;
  width: 20px;
  height: 20px;
  background-color: red;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-content: center;
}
</style>
