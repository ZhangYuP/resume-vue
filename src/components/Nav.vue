<template>
  <nav class="clearfix">
    <a class="logo" href="#">
      <span class="family-name">Z</span><span class="given-name">YP</span>
    </a>
    <ul class="clearfix">
      <li><a href="#">关于</a></li>
      <li><a href="#">技能</a></li>
      <li><a href="#">经历</a></li>
      <li>
        <a href="#">作品
          <ul class="submenu">
            <li v-for="(item, index) in portfolio" v-bind:key="index"><a href="">{{item}}</a></li> 
          </ul>
        </a>
      </li>
      <li><a href="#">留言</a></li>
      <li><a href="#">下载</a></li>
    </ul>
  </nav>
</template>

<script>
  export default {
    name: "Nav",
    data(){
      return {
        portfolio: ['随机音乐', '仿cnode社区', '鹏UI', '极简清单', 'canvas画板', '画一只皮卡丘']
      }
    },
    mounted(){
      window.scrollY > 0 ? this.active() : this.deactive()
      window.addEventListener('scroll', () => {window.scrollY > 0 ? this.active() : this.deactive()})
    },
    methods: {
      active(){
        this.$el.classList.add('sticky')
      },
      deactive(){
        this.$el.classList.remove('sticky')
      }
    }
  }
</script>

<style scoped lang="scss">
  @keyframes menuSlide {
    0%{
      left: 50%; width: 0;
    }
    100%{
      left: 0; width: 100%;
    }
  }
  .clearfix::after{
    content: '';
    display: block;
    clear: both;
  }
  nav{
    position: fixed;
    top: 0;
    left: 0;
    font-size: 14px;
    color: #b7b7b7;
    height: 80px;
    width: 100%;
    padding: 20px;
    line-height: 40px;
    &.sticky{
      background-color: #ffffff;
      height: 60px;
      padding: 10px 20px;
      box-shadow: 0 0 10px rgba($color: #000000, $alpha: 0.25);
      color: #3d4451;
    }
    .logo{
      font-size: 24px;
      font-family: 'Arial Black';
      margin-left: 15px;
      .family-name{
        color: #e6686a;
      }
      .given-name{
        color: #9a9da2;
      }
    }
    >ul{
      float: right;
      margin-right: -5px;
      >li{
        float: left;
        margin-left: 15px;
        margin-right: 15px;
        &:hover{
          >a::after{
            border-bottom: 3px solid #e6686a;
            animation: menuSlide 0.5s;
          }
        }
        >a{
          position: relative;
          font-weight: bold;
          padding: 5px;
          &::after{
            content: '';
            display: block;
            width: 100%;
            position: absolute;
            top: 100%;
            left: 0;
          }
        }
        .submenu{
          background-color: rgba(255,255,255,0.9);
          box-shadow: 0 1px 4px rgba($color: #000000, $alpha: 0.5);
          position: absolute;
          top: 32px;
          left: 0;
          color: #3d4451;
          >li{
            line-height: 30px;
            white-space: nowrap;
            &:hover{
                color: #ffffff;
                background-color: #e6686a;
            }
            >a{
              font-weight: normal;
              padding: 5px;
            }
          }
        }
      }
    }
  }
</style>
