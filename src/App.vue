<template>
  <div id="app">
    <Header />
    <AddTodo v-on:add-todo="addTodo" />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import AddTodo from './components/AddTodo.vue';
import Todos from './components/Todos.vue';

  export default {
    name: 'app',
    components: {
      Header,
      Todos,
      AddTodo
    },
    data(){
      return{
        todos: [
          {
            id: 1,
            title: "Todo One",
            completed: false
          },
          {
            id: 2,
            title: "Todo Two",
            completed: true
          },
          {
            id: 3,
            title: "Todo Three",
            completed: false
          },
        ]
      }
    },
    methods: {
      deleteTodo(id){
        this.todos = this.todos.filter(todo => todo.id != id);
      },
      addTodo(newTodo) {
        this.todos = [...this.todos, newTodo];
      }
    }
  }
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body{
  margin: 100px;
  font-family: sans-serif, Arial;
  line-height: 1.4;
}

.btn {
  display: inline-block;
  border: none;
  background: green;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}

.btn:hover {
  background: rgba(1, 156, 1, 0.815);
}

</style>






