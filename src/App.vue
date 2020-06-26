<template>
  <div id="app">
    <jokes/>
  </div>
</template>

<script>
import jokes from './components/jokes.vue'
export default {
  name: 'App',
  components: {
    jokes
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Oswald:wght@200;300;400;500;600;700&family=Source+Sans+Pro:wght@400;600;700&display=swap');
body{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Source Sans Pro', sans-serif;
}
</style>
