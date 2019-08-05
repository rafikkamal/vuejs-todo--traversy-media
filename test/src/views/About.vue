<template>
  <div class="about">
    <Header headerTitle='About Us'/>
    <p>
      This is an about page.<br/>
      Check the <a href="https://www.youtube.com/watch?v=Wy9q22isx3U">youtube link</a> for more idea.
    </p>
  </div>
</template>
<script>
import Header from "../components/layout/Header.vue";

export default {
  name: 'About',
  components: {
    Header
  }
}
</script>

<style scoped>
  p {
    text-align: center;
    padding: 10px;
  }
</style>
