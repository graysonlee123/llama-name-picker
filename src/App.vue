<template>
  <div id="app">
    <navbar></navbar>
    <hero></hero>
    <featured></featured>
    <div class="container mx-auto my-8">
      <description-list></description-list>
    </div>
  </div>
</template>

<script>
import Hero from './components/Hero.vue'
import Featured from './components/Featured.vue'
import Navbar from './components/Navbar.vue'
import DescriptionList from './components/DescriptionList.vue'

export default {
  components: {
    Hero,
    Featured,
    Navbar,
    DescriptionList,
  },
}
</script>

<style>
body {
  background-color: lightblue;
}
</style>
