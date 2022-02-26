<template>
    <div >
    <div class=" grey darken-4">
      <Search v-on:query-change="querySearch" />
    </div>

      <h2 class="center-align">Gym</h2>

    <div  class=" container">
      <h2 class="">Rutina  <a class="btn-floating btn-large waves-effect waves-light teal right  btn modal-trigger" href="#modal1">
            <i class="material-icons">add</i></a> </h2>
      <TodoAdd v-on:add-todo="addTodo" />
      <Todos v-bind:todoslist="copyTodos" v-on:delete-todo="deleteTodo" />
    </div>
    </div>
</template>

<script>

import Search from './components/Search';
import Todos from './components/Todos';
import TodoAdd from './components/TodoAdd';
import M from 'materialize-css'

export default {
  name: 'App',
  mounted () {
    M.AutoInit()
},
  components: {
    Todos, TodoAdd, Search
  },
  methods: {
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id != id);
      this.copyTodos = [...this.todos];
    },
    addTodo(todo){
      this.todos.push(todo);
      this.copyTodos = [...this.todos];
    },
    querySearch(query){
      if(query.trim() === ''){
        this.copyTodos = [...this.todos];
      }else{
        const temp = this.todos.filter(todo =>{
          return todo.title.includes(query)
        });
        this.copyTodos = [...temp];
      }
    }
  },
  data(){
    return {
      todos: [  ],
      copyTodos: []
    }
  },
  created(){
    this.copyTodos = [...this.todos];
  }
}
</script>

<style>
  /*body{
    font-family: Arial, Helvetica, sans-serif;
    font-size: 1.5em;
    padding: 0;
    margin: 0;
    background-color: azure;
  }
  #main-container{
    border: solid 1px #ccc;
    width: 800px;
    margin: 80px auto;
    background-color:#f9f9f9;
  }

*/

 
</style>