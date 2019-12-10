<template>
  <div id="app">
    <Nav />
    <Banner />
    <About />
    <Skill />
    <Experience />
    <Portfolio />
    <Message />
  </div>
</template>

<script>
import Nav from './components/Nav';
import Banner from './components/Banner';
import About from './components/About';
import Skill from './components/Skill';
import Experience from "./components/Experience";
import Portfolio from "./components/Portfolio";
import Message from "./components/Message";

export default {
  name: 'app',
  components: {
    Nav,
    Banner,
    About,
    Skill,
    Experience,
    Portfolio,
    Message
  }
}
</script>

<style lang="scss">
#app {
  section {
    width: 900px;
    margin: 30px auto;
    %box{
      background: #ffffff;
      padding: 25px 50px;
      margin-top: 30px;
      box-shadow: 0 1px 6px rgba(0, 0, 0, 0.12), 0 1px 4px rgba(0, 0, 0, 0.24);
    }
    > ol {
      @extend %box;
      > li {
        padding: 10px 0;
      }
    }
    .messageboard{
      @extend %box;
    }
  }
}
</style>
