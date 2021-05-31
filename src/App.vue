<template>
  <tophead/>
  <maincontent/>
  <mainfooter/>
</template>

<script>
import tophead from './components/tophead.vue'
import maincontent from './components/maincontent.vue'
import mainfooter from './components/mainfooter'


export default {
  name: 'App',
  components: { 
    tophead,
    maincontent,
    mainfooter,
    
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
  margin-top: 60px;
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

.container {
    max-width: 1440px;
    margin: 0 auto;
}
</style>
