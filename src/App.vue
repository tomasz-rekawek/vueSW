<template>
  <div id="app">
    <img src="./assets/logo.png">
    <ActorsList/>
  </div>
</template>

<script>
import ActorsList from './components/ActorsList.vue'

export default {
  name: 'app',
  components: {
    ActorsList
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
