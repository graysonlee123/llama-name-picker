<template>
  <div id="app">
    <navbar></navbar>
    <input></input>
    <p>
      {{ message }}
    </p>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'
import Input from './components/Input.vue'

export default {
  components: {
    Navbar,
    Input
  },
  data() {
    return {
      message: 'Hello world',
    }
  },
}
</script>

<style>
#app {
  font-size: 1rem;
  font-family: 'Helvetica', 'Roboto', sans-serif;
  color: blue;
}

body {
  background-color: tomato;
}
</style>
