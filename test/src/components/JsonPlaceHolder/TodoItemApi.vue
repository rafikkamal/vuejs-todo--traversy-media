<template>
  <div>
    <p class="todo-item" v-bind:class="{'is-complete':todo.completed}">
      <input type="checkbox" v-model="todo.completed" v-on:input="markComplete">
      {{todo.title}}
      <button class="del" @click="$emit('del-todo-json', todo.id)">x</button>
    </p>
  </div>
</template>
<script>
  export default {
    name: "TodoItemApi",
    props: ["todo"],
    methods: {
      markComplete() {
        this.todo.completed = !this.todo.completed;
      }
    }
  }
</script>
<style scoped>
  .todo-item {
    background: #f4f4f4;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
  }
  .is-complete {
    text-decoration: line-through;
  }
  .del {
    background: #ff0000;
    color: #ffffff;
    border: none;
    padding: 3px 9px 5px 8px;
    border-radius: 50%;
    cursor: pointer;
    float: right;
  }
</style>
