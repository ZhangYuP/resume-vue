<template>
  <section id="experience">
    <h2>经历</h2>
    <ol>
      <li>
        <h3>教育经历</h3>
        <dl class="clearfix">
          <dt>2010.09 ~ 2014.06</dt>
          <dd>在中南大学土木工程专业学习。</dd>
        </dl>
      </li>
      <li>
        <h3>工作经历</h3>
        <dl class="clearfix">
          <dt>2014.07 ~ 2014.10</dt>
          <dd>在中建八局第三建设有限公司，南京证大喜玛拉雅中心项目从事施工员工作。</dd>
          <dt>2014.12 ~ 2018.08</dt>
          <dd>在广东省电信规划设计院有限公司南京分公司，从事通信工程配套土建结构设计工作。</dd>
        </dl>
      </li>
    </ol>
  </section>
</template>

<script>
  export default {
    name: "Experience"
  }
</script>

<style scoped lang="scss">
  #experience{
    @mixin cell($width){
      width: $width;
      float: left;
      padding: 5px 0;
    }
    dt{
      font-weight: bold;
      @include cell(25%);
    }
    dd{
      @include cell(75%);
    }
  }
</style>
