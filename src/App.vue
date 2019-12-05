<template>
  <div id="app">
    <Nav />
    <Banner />
  </div>
</template>

<script>
import Nav from './components/Nav'
import Banner from './components/Banner'

export default {
  name: 'app',
  components: {
    Nav,
    Banner
  }
}
</script>

<style>
#app {

}
</style>
