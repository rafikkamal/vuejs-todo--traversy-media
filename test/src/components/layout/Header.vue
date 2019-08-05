<template>
  <header>
    <h1>{{ headerTitle }}</h1>
  </header>
</template>

<script>
  export default {
    name: "Header",
    props: {
      headerTitle: String
    },
    data() {
      return {
        title: "this is a title",
        message: "this is a message"
      }
    }
  }
</script>

<style scoped>
  header {
    background: #333;
    color: #fff;
    text-align: center;
    padding: 10px;
  }
  header a {
    color: #fff;
    padding-right: 5px;
  }
</style>
