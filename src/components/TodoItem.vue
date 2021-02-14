<template>
  <div>
      <div class="todo-item">
        {{todo.title}}
        <i @click="$emit('del-todo',todo.id)" class="del-todo fa fa-times"></i>
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
  }
}
</script>

<style scoped>
.todo-item{
  background-color: #ffb997;
  padding: 10px 20px;
  border-bottom: 1px solid #0b032d;
}
.del-todo{
  float: right;
  cursor: pointer;
}
.todo-item.isCompleted{
  text-decoration: line-through;
}
</style>