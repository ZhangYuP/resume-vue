<template>
  <div id="app">
    <Nav />
    <Banner />
    <About />
    <Skill />
  </div>
</template>

<script>
import Nav from './components/Nav'
import Banner from './components/Banner'
import About from './components/About'
import Skill from './components/Skill'

export default {
  name: 'app',
  components: {
    Nav,
    Banner,
    About,
    Skill
  }
}
</script>

<style>
#app {

}
</style>
