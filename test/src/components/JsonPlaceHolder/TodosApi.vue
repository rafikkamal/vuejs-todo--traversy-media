<template>
  <div>
    <div v-bind:key="todo.id" v-for="todo in todosJSON">
      <TodoItemApi v-bind:todo="todo" v-on:del-todo-json="$emit('del-todo-json', todo.id)" />
    </div>
  </div>
</template>
<script>
  import TodoItemApi from "./TodoItemApi.vue";
  export default {
    name: "TodosApi",
    components: {
      TodoItemApi
    },
    props: ["todosJSON"]
  }
</script>
<style scoped>

</style>
