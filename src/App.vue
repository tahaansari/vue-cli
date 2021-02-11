<template>
  <div>
    <todos :todos="todos" @del-todo="deltodo"/>
  </div>
</template>

<script>

import todos from './components/Todos'

export default {
  name: 'App',
  components:{
    todos
  },
  data(){
    return{
      todos:[
        {
          id:1,
          title:"task 1",
          completed:false
        },
        {
          id:2,
          title:"task 2",
          completed:false
        },
        {
          id:3,
          title:"task 3",
          completed:false
        },
        {
          id:4,
          title:"task 4",
          completed:false
        },
        {
          id:5,
          title:"task 5",
          completed:false
        }
      ]
    }
  },
  methods:{
    deltodo(id){
      this.todos = this.todos.filter( todo => todo.id != id )
    }
  }
}
</script>

<style>
*{margin: 0;padding: 0}
</style>