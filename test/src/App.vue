<template>
  <div id="app">
    <Nav/>
  </div>
</template>

<script>
  import Nav from './components/layout/Nav';
  export default {
    name: 'app',
    components: {
      Nav
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
</style>
