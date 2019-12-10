<template>
  <section id="portfolio">
    <h2>作品</h2>
    <ol>
      <li class="clearfix">
        <img src="../../public/works/randommusic.jpg" alt="随机音乐" width="300px" height="169px">
        <div class="description">
          <h3>随机音乐</h3>
          <span class="showLink">
            <a href="https://zhangyup.github.io/random-music/" target="_blank">预览链接</a>
            <a href="https://github.com/ZhangYuP/random-music" target="_blank">源码链接</a>
          </span>
          <hr>
          <p>
            描述：主要使用<strong>原生 JavaScript</strong> 实现的一个网页版音乐播放器，用 <strong>ajax</strong> 请求音乐数据，
            使用 <strong>Audio 对象</strong>的 API 来控制音乐播放，运用了 <strong>MVC</strong> 的思想，通过<strong>自定义事件</strong>实现模块之间的事件交互，
            实现了音乐播放、暂停、切换歌曲、进度控制、歌词滚动、歌曲收藏等功能。
          </p>
        </div>
      </li>
      <li class="clearfix">
        <img src="../../public/works/cnode.jpg" alt="仿cnode社区" width="300px" height="169px">
        <div class="description">
          <h3>仿cnode社区</h3>
          <span class="showLink">
              <a href="https://zhangyup.github.io/cnode/#/" target="_blank">预览链接</a>
              <a href="https://github.com/ZhangYuP/cnode" target="_blank">源码链接</a>
            </span>
          <hr>
          <p>
            描述：该项目使用 <strong>Vue</strong> 仿写了 cnode 社区。项目利用 cnode 社区提供的 API，使用 <strong>Axios</strong> 获取数据，
            使用 <strong>Vue Router</strong> 进行路由切换和传参，使用 <strong>webpack</strong> 进行打包。实现帖子的分类查看、查看作者信息等功能。
          </p>
        </div>
      </li>
      <li class="clearfix">
        <img src="../../public/works/rocui.jpg" alt="鹏UI" width="300px" height="169px">
        <div class="description">
          <h3>鹏UI</h3>
          <span class="showLink">
              <a href="https://zhangyup.github.io/roc-ui/" target="_blank">预览链接</a>
              <a href="https://github.com/ZhangYuP/roc-ui" target="_blank">源码链接</a>
            </span>
          <hr>
          <p>
            描述：该项目是一个基于 <strong>Vue</strong> 的简易<strong>UI 组件库</strong>，目前已包含按钮、输入框、栅格、布局、手风琴、Toast、Tab、Popover 等组件。
            每个组件均经历了从<strong>需求分析</strong>到<strong> Mocha 单元测试</strong>，并用 <strong>Travis CI</strong>
            实现<strong>持续集成</strong>，
            通过 <strong>VuePress</strong> 制作了官方文档。代码已发布到 npmjs.org。
          </p>
        </div>
      </li>
      <li class="clearfix">
        <img src="../../public/works/simpletodo.jpg" alt="极简清单" width="300px" height="169px">
        <div class="description">
          <h3>极简清单</h3>
          <span class="showLink">
              <a href="https://zhangyup.github.io/Simple-Todo/build/index.html" target="_blank">预览链接</a>
              <a href="https://github.com/ZhangYuP/Simple-Todo" target="_blank">源码链接</a>
            </span>
          <hr>
          <p>
            描述：主要使用 <strong>React</strong> 实现的一个 ToDo List，使用 <strong>LeanCloud</strong> 存储用户信息和 ToDo 数据，
            使用 <strong>webpack</strong> 进行打包。实现了账号注册、登录、找回密码，Todo 的创建、标记、删除、复原等功能。
          </p>
        </div>
      </li>
      <li class="clearfix">
        <img src="../../public/works/canvas.jpg" alt="canvas画板" width="300px" height="169px">
        <div class="description">
          <h3>canvas画板</h3>
          <span class="showLink">
              <a href="https://zhangyup.github.io/canvas/index.html" target="_blank">预览链接</a>
              <a href="https://github.com/ZhangYuP/canvas" target="_blank">源码链接</a>
            </span>
          <hr>
          <p>
            描述：使用<strong>原生 JavaScript</strong> 实现的一个简易在线画板，主要使用 HTML 5 的 <strong>Canvas API</strong>，
            实现了 PC 和移动端在线画图、橡皮擦、选择画笔大小、选择画笔颜色、清除、保存画作等功能。
          </p>
        </div>
      </li>
      <li class="clearfix">
        <img src="../../public/works/pikachu.jpg" alt="画一只皮卡丘" width="300px" height="169px">
        <div class="description">
          <h3>画一只皮卡丘</h3>
          <span class="showLink">
              <a href="https://zhangyup.github.io/make-a-pikachu/" target="_blank">预览链接</a>
              <a href="https://github.com/ZhangYuP/make-a-pikachu" target="_blank">源码链接</a>
            </span>
          <hr>
          <p>
            描述：使用<strong>原生 JavaScript</strong> 写的一个动态显示 CSS 画皮卡丘过程的小作品。用<strong>定时器</strong>遍历一段预先写在
            <strong>preview</strong>
            标签内的代码，将其依次展示在页面上，并依次写入 <strong>style</strong> 标签内，以使 CSS 生效。此外，还增加了代码高亮效果，并实现了调速功能。
          </p>
        </div>
      </li>
    </ol>
  </section>
</template>

<script>
  export default {
    name: "Portfolio"
  }
</script>

<style scoped lang="scss">
  #portfolio > ol > li{
    padding: 20px 0;
  }
  img{
    float: left;
    box-shadow: 0 5px 11px 0 rgba(0, 0, 0, 0.18), 0 4px 15px 0 rgba(0, 0, 0, 0.15);
  }
  .description{
    float: left;
    width: 440px;
    margin-left: 60px;
    line-height: 1.5;
    position: relative;
    hr{
      margin-bottom: 5px;
    }
    .showLink{
      position: absolute;
      top: 8px;
      right: 0;
      a{
        margin-left: 4em;
        color: #00bfff;
        &:hover{
          color: darken(#00bfff, 10%);
        }
      }
    }
  }
</style>
