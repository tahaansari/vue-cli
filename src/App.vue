<template>
  <div>
    <appheader/>
    <todos :todos="todos" @del-todo="deltodo"/>
  </div>
</template>

<script>

import appheader from './components/AppHeader'
import todos from './components/Todos'

export default {
  name: 'App',
  components:{
    appheader,
    todos
  },
  data(){
    return{
      todos:[]
    }
  },
  methods:{
    deltodo(id){
      this.todos = this.todos.filter( todo => todo.id != id )
    }
  },
  created(){
    fetch('https://jsonplaceholder.typicode.com/todos/')
    .then( res=>res.json() )
    .then( res=> this.todos = res )
    .catch( err=> console.log(err) )
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');
@import url('https://stackpath.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css');

/* RESET CSS */
a,abbr,acronym,address,applet,article,aside,audio,b,big,blockquote,body,canvas,caption,center,cite,code,dd,del,details,dfn,div,dl,dt,em,embed,fieldset,figcaption,figure,footer,form,h1,h2,h3,h4,h5,h6,header,hgroup,html,i,iframe,img,ins,kbd,label,legend,li,mark,menu,nav,object,ol,output,p,pre,q,ruby,s,samp,section,small,span,strike,strong,sub,summary,sup,table,tbody,td,tfoot,th,thead,time,tr,tt,u,ul,var,video{margin:0;padding:0;border:0;font-size:100%;font:inherit;vertical-align:baseline}article,aside,details,figcaption,figure,footer,header,hgroup,menu,nav,section{display:block}body{line-height:1}ol,ul{list-style:none}blockquote,q{quotes:none}blockquote:after,blockquote:before,q:after,q:before{content:'';content:none}table{border-collapse:collapse;border-spacing:0}
/* RESET CSS */
body{
  font-family: 'Roboto', sans-serif;
  padding: 40px;
}
</style>