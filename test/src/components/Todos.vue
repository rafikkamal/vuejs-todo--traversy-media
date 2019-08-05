<template>
  <div>
    <h1>Todos</h1>
    <div>
      <h3 v-bind:key="todo.id" v-for="todo in todos" class="todos">{{todo.title}}</h3>
    </div>
  </div>
</template>
<script>
  export default {
    name: "Todo",
    props: ["todos"]
  }
</script>
<style scoped>

</style>
