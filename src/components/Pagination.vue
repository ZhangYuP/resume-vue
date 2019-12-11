<template>
  <ol class="pages">
    <li v-for="(page, index) in pages" :key="index" :class="isactive === index ? 'active' : ''"
      v-on:click="clickPage(index)">
      {{page + 1}}
    </li>
  </ol>
</template>

<script>
  export default {
    name: "Pagination",
    data(){
      return {
        pages: [],
        isactive: 0,
      }
    },
    mounted(){
      this.$eventBus.$on('sendCount', allCount => {
        this.showPages(allCount)
      })
    },
    methods: {
      showPages(allCount){
        var p = parseInt(allCount / 10) + 1
        this.pages = Array.from(Array(p),(value, key) => key)
      },
      clickPage(index){
        this.isactive = index
        this.$eventBus.$emit('changePage', index)
      }
    }
  }
</script>

<style scoped lang="scss">
  .pages{
    text-align: center;
    li{
      display: inline-block;
      padding: 2px 8px;
      margin: 16px 8px;
      border: 1px solid #cdcfd1;
      border-radius: 2px;
      cursor: pointer;
      &:hover{
        box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.18), 0 3px 4px 0 rgba(0, 0, 0, 0.15);
      }
      &.active{
        background: #e6686a;
        border-color: #e6686a;
        color: #ffffff;
        box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.18), 0 3px 4px 0 rgba(0, 0, 0, 0.15);
      }
    }
  }
</style>
