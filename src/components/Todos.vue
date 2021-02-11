<template>
  <div>
    <ul>
      <li v-for="todo in todos" :key="todo.id">
        <todoitem :todo="todo" @del-todo="$emit('del-todo',todo.id)"/>
      </li>
    </ul>
  </div>
</template>

<script>
import todoitem from './TodoItem'
export default {
  name: 'Todos',
  components:{
    todoitem
  },
  props:['todos']
} 
</script>

<style scoped>
.title{
  text-align: center;
}
</style>