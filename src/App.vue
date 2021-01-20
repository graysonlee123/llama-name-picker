<template>
  <div id="app">
    <navbar></navbar>
    {{ message }}
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'

export default {
  components: {
    Navbar,
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
