<template>
  <div class="banner">
    <div class="mask"></div>
  </div>
</template>

<script>
  export default {
    name: "Banner"
  }
</script>

<style scoped lang="scss">
  $height: 500px;
  .banner{
    height: $height;
    background:{
      image: url(../../public/rs-cover.jpg);
      position: center center;
      size: cover;
    }
    .mask{
      height: $height;
      background-color: rgba($color: #000000, $alpha: 0.8);
    }
  }
</style>
