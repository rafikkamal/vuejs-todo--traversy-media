<template>
  <div id="app">
    <Header headerTitle='Todo List'/>
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
    <br/>
    <Header headerTitle='Todo List Using JsonPlaceHolder'/>
    <AddTodoApi v-on:add-todo-json="addTodoJSON"/>
    <TodosApi v-bind:todosJSON="todosJSON" v-on:del-todo-json="deleteTodoJSON"/>
  </div>
</template>

<script>
import Header from "./components/layout/Header.vue";
import axios from "axios";
/**
 * Basic implementation
 */
import Todos from "./components/Todos.vue";
import AddTodo from "./components/AddTodo.vue";
/**
 * New imports for getting data using API
 * JSON Place Holder
 */
import TodosApi from "./components/JsonPlaceHolder/TodosApi.vue";
import AddTodoApi from "./components/JsonPlaceHolder/AddTodoApi.vue";

export default {
  name: 'app',
  components: {
    Todos, Header, AddTodo, TodosApi, AddTodoApi
  },
  data() {
    return {
      todos : [
        {
          id: 1,
          title: "Todo One",
          completed: false
        },
        {
          id: 2,
          title: "Todo Two",
          completed: false
        },
        {
          id: 3,
          title: "Todo Three",
          completed: true
        },
        {
          id: 4,
          title: "Todo Four",
          completed: false
        }
      ],
      todosJSON : []
    }
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo];
    },
    deleteTodoJSON(id) {
      this.todosJSON = this.todosJSON.filter(todo => todo.id !== id);
    },
    addTodoJSON(newTodo) {
      /* Destructuring */
      const { title, completed } = newTodo;
      axios.post("https://jsonplaceholder.typicode.com/todos", {
        title, completed
      })
      .then(res => this.todosJSON = [...this.todosJSON, res.data])
      .catch(err => console.log(err));
    }
  },
  created() {
    axios.get("https://jsonplaceholder.typicode.com/todos?_limit=10")
    .then(res => this.todosJSON = res.data)
    .catch(err => console.log(err));
    console.log(this.todosJSON.length);
  }
}
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }
  .btn {
    display: inline-block;
    border: none;
    background: #555;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
  }
  .btn:hover {
    background: #666;
  }
  form {
    margin: 2px auto;
  }
</style>
