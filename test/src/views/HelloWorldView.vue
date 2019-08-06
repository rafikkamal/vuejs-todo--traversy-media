<template>
  <div>
    <Header headerTitle='Hello World'/>
    <HelloWorld msg="This is an helloworld page."/>
  </div>
</template>

<script>
  import Header from "../components/layout/Header.vue";
  import HelloWorld from "../components/HelloWorld.vue";
  export default {
    name: 'HelloWorldView',
    components: {
      Header, HelloWorld
    }
  }
</script>

<style scoped>
  p {
    text-align: center;
    padding: 10px;
  }
</style>
