<template>
  <div>
    <navBar></navBar>
    <div class="bg-light">
      <banner class="banner"></banner>
      <section>
        <div class="section-title">
          <h2>就业班</h2>
          <small>零基础快速就业</small>
        </div>
        <job-class></job-class>
      </section>
      <section>
        <div class="section-title">
          <h2>职场进阶</h2>
          <small>1年以上开发经验系统成长</small>
        </div>
        <improve></improve>
      </section>
    </div>
    <div class="bg-dark">
      <section>
        <div class="section-title">
          <h2>新上好课</h2>
        </div>
        <new-lesson></new-lesson>
      </section>
    </div>
    <div class="bg-light">
      <learn-route></learn-route>
    </div>
    <div class="bg-dark">
      <popular-lesson></popular-lesson>
    </div>
    <div class="bg-light">
      <section>
        <div class="section-title">
          <h2>慕课专栏</h2>
          <a class="more" href="#">查看更多 <i class="imv2-right2"></i></a>
        </div>
        <read></read>
      </section>
    </div>
  </div>
</template>

<script>
import banner from './index/Banner'
import navBar from './index/Nav'
import jobClass from './index/JobClass'
import improve from './index/Improve'
import newLesson from './index/NewLessons'
import learnRoute from './index/LearnRoute'
import popularLesson from './index/PopularLesson'
import read from './index/Read'
export default {
  name: 'Index',
  components: {
    banner: banner,
    navBar: navBar,
    jobClass: jobClass,
    improve: improve,
    newLesson: newLesson,
    learnRoute: learnRoute,
    popularLesson: popularLesson,
    read: read
  }
}
</script>

<style lang="scss" scoped>
  .banner {
    margin: 100px auto 0 auto;
    z-index: 1;
    box-shadow: 0 20px 20px #b4b4b4;
  }

  .bg-light {
    overflow:hidden;
    background-color: #fff;
    padding-bottom: 44px;
  }

  .bg-dark {
    overflow:hidden;
    background-color: #f7f9fb;
    padding-bottom: 44px;
    box-shadow: inset 0 10px 10px -10px #dddddd, inset 0 -10px 10px -10px #eeeeee;
  }
</style>

<style lang="scss">
  section {
    width: 1152px;
    margin: 48px auto 0 auto;
    .section-title {
      overflow: hidden;
      line-height: 30px;
      h2 {
        font-size: 24px;
        float: left;
      }
      small {
        margin-left: 14px;
        color: #414a51;
        font-size: 13px;
        float: left;
      }
      .more {
        float: right;
        margin-top: 2px;
        line-height: 24px;
        color: #1C1F21;
        font-size: 14px;
        font-weight: normal;
        position: relative;
        top: -4px;
      }
    }
    .container {
      margin-top: 24px;
    }
  }
</style>
