<template>
  <div id="app">
    <Nav />
    <Banner />
    <About />
  </div>
</template>

<script>
import Nav from './components/Nav'
import Banner from './components/Banner'
import About from './components/About'

export default {
  name: 'app',
  components: {
    Nav,
    Banner,
    About
  }
}
</script>

<style>
#app {

}
</style>
