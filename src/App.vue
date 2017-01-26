<template>
  <div id="app">
    <couplet></couplet>
    <footer>
      <label>横批<input type="text"></label>
    </footer>
  </div>
</template>

<script>
import Hello from './components/Hello'
import couplet from './components/couplet'

export default {
  name: 'app',
  components: {
    Hello,
    couplet
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  
}
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
