<template>
  <Main/>
</template>

<script>
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
      Main
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
a {
    color: #1d31ff;
    font-size: 10px;
}
.title{
    font-size: 20px;
}
.description{
    font-size: 10px;
}
</style>
