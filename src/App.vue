<template>
  <div id="app">
    {{ message }}
  </div>
</template>

<script>
export default {
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
</style>
