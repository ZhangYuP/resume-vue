<template>
  <section class="about">
    <main class="clearfix">
      <div class="picture">
        <img src="../../public/zyp.jpg" width="260" height="260" alt="头像">
        <span class="welcome">Hello
          <span class="triangle"></span>
        </span>
      </div>
      <div class="text">
        <a id="downloadResume" href="./前端-张玉鹏的个人简历.pdf" target="_blank" download>下载PDF简历</a>
        <a id="openHtml" href="https://zhangyup.github.io/resume/index.html" target="_blank" title="网页版简历">查看网页版简历</a>
        <h1>张玉鹏</h1>
        <p>应聘前端开发工程师职位。自学前端一年。目前离职状态，一周内可到岗。</p>
        <hr>
        <dl class="clearfix">
          <dt>年龄</dt>
          <dd>27</dd>
          <dt>性别</dt>
          <dd>男</dd>
          <dt>城市</dt>
          <dd>南京</dd>
          <dt>学校</dt>
          <dd>中南大学</dd>
          <dt>专业</dt>
          <dd>土木工程</dd>
          <dt>英语</dt>
          <dd>CET-6</dd>
          <dt>邮箱</dt>
          <dd>zyp5318@qq.com</dd>
          <dt>手机</dt>
          <dd>18205084006</dd>
        </dl>
        <img src="../../public/weixin.jpg" alt="微信二维码">
      </div>
    </main>
    <footer class="media">
      <a href="https://github.com/ZhangYuP" target="_blank" title="github主页">
        <svg class="icon" aria-hidden="true">
          <use xlink:href="#icon-github"></use>
        </svg>
      </a>
      <a href="https://www.jianshu.com/u/97f69481bf82" target="_blank" title="简书主页">
        <svg class="icon" aria-hidden="true">
          <use xlink:href="#icon-jianshu"></use>
        </svg>
      </a>
      <a href="https://tuchong.com/2563865/posts" target="_blank" title="图虫主页">
        <svg class="icon" aria-hidden="true">
          <use xlink:href="#icon-tuchong"></use>
        </svg>
      </a>
      <a href="javascript:" title="微信二维码" id="weixin" ref="weixin">
        <svg class="icon" aria-hidden="true">
          <use xlink:href="#icon-weixin"></use>
        </svg>
        <img src="../../public/weixin.jpg" alt="微信二维码">
      </a>
    </footer>
  </section>
</template>

<script>
  export default {
    name: "About",
    mounted(){
      this.$refs.weixin.addEventListener('click', e => {
        e.stopPropagation()
        this.$refs.weixin.lastElementChild.classList.add('active')
        document.addEventListener('click', () => {
          this.$refs.weixin.lastElementChild.classList.remove('active')
        })
      })
    }
  }
</script>

<style scoped lang="scss">
  $white: #ffffff;
  $grey: #cdcfd1;
  $red: #e6686a;
  .about{
    max-width: 940px;
    margin: -350px auto 0;
    background-color: $white;
    box-shadow: 0 1px 6px rgba(0, 0, 0, 0.12), 0 1px 4px rgba(0, 0, 0, 0.24);
    main{
      padding: 50px;
      .picture{
        float: left;
        position: relative;
        img{
          vertical-align: top;
        }
        .welcome{
          display: inline-block;
          background-color: $red;
          color: $white;
          border-radius: 4px;
          padding: 4px 15px;
          position: absolute;
          top: -20px;
          right: -10px;
          .triangle{
            display: block;
            border: 10px solid transparent;
            border-top-width: 0;
            border-left-color: $red;
            position: absolute;
            top: 100%;
            left: 5px;
          }
        }
      }
      .text{
        float: left;
        margin-left: 80px;
        width: 500px;
        position: relative;
        #openHtml{
          display: none;
        }
        #downloadResume{
          font-size: 14px;
          font-weight: bold;
          line-height: 14px;
          padding: 10px 20px;
          border: 1px solid $grey;
          border-radius: 4px;
          position: absolute;
          top: -5px;
          right: 0;
          &:hover{
            box-shadow: 0 5px 11px 0 rgba(0, 0, 0, 0.18), 0 4px 15px 0 rgba(0, 0, 0, 0.15);
          }
        }
        h1{
          margin-bottom: 20px;
          font-weight: bold;
        }
        hr{
          margin: 15px 0;
        }
        dl{
          %table{
            float: left;
            padding: 5px;
          }
          dt{
            @extend %table;
            width: 12%;
            font-weight: bold;
          }
          dd{
            @extend %table;
            width: 38%;
          }
        }
        img{
          display: none;
          position: absolute;
          width: 122px;
          height: 122px;
          bottom: 1px;
          right: -7px;
        }
      }
    }
    footer{
      background-color: $red;
      text-align: center;
      a{
        display: inline-block;
        border-radius: 50%;
        line-height: 30px;
        padding: 10px;
        margin: 10px 20px;
        &:hover{
          background: #d05d60;
        }
        svg{
          width: 30px;
          height: 30px;
          fill: $white;
          vertical-align: top;
        }
        &#weixin{
          position: relative;
          img{
            position: absolute;
            width: 0;
            height: 0;
            top: 25px;
            left: 25px; 
            opacity: 0;
            box-shadow: 0 5px 11px 0 rgba(0, 0, 0, 0.18), 0 4px 15px 0 rgba(0, 0, 0, 0.15);
            transition: all 0.3s ease-in;
            &.active{
              width: 250px;
              height: 250px;
              top: -100px;
              left: -100px;
              opacity: 1;
            }
          }
        }
      }
    }
  }
</style>
