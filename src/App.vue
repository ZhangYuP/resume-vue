<template>
  <div id="app">
    <Nav />
    <Banner />
    <About />
    <Skill />
    <Experience />
  </div>
</template>

<script>
import Nav from './components/Nav'
import Banner from './components/Banner'
import About from './components/About'
import Skill from './components/Skill'
import Experience from "./components/Experience"

export default {
  name: 'app',
  components: {
    Nav,
    Banner,
    About,
    Skill,
    Experience
  }
}
</script>

<style lang="scss">
#app {
  section {
    width: 940px;
    margin: 30px auto;
    > ol {
      background: #ffffff;
      padding: 25px 50px;
      margin-top: 30px;
      box-shadow: 0 1px 6px rgba(0, 0, 0, 0.12), 0 1px 4px rgba(0, 0, 0, 0.24);
      > li {
        padding: 10px 0;
      }
    }
  }
}
</style>
