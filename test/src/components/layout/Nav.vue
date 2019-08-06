<template>
  <div>
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/helloworld">HelloWorld</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/>
  </div>
</template>

<script>
  export default {
    name: 'nav'
  }
</script>

<style>
  div#nav {
    text-align: center;
    padding: 5px;
    font-weight: bold;
  }
  div#nav a {
    color: #fff;
    text-decoration: none;
    padding: 5px 10px;
  }
</style>
