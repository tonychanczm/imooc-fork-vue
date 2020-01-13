<template>
  <div class="card">
    <a :href="route.href">
      <div class="image">
        <img class="bottom" :src="route.img"/>
        <img class="middle" :src="route.img"/>
        <img class="top" :src="route.img"/>
      </div>
      <h4>{{route.title}}</h4>
      <p>{{route.desc}}</p>
      <div class="info">
        <span>{{route.step}}步骤 · {{route.lesson}}门课</span>
        <span><i class="imv2-star2"></i>{{route.favourite}}人收藏</span>
      </div>
    </a>
  </div>
</template>

<script>
/*
   title: '从零开始，实现Python Flask入门到高阶',
   desc: '路线专为零Flask基础的学员定制，我们从Flask最基础的框架开始到多种热门项目实战，层层深入，一站式教程，助你熟练掌握Flask 核心开发。',
   img: '/ss/sss/s',
   href: 'sssssss',
   step: 4,
   lesson: 4,
   favourite: 2751
*/
export default {
  name: 'LearnRouteCard',
  props: {
    route: Object
  }
}
</script>

<style lang="scss" scoped>
.card {
  float: left;
  margin-left: 24px;
  margin-bottom: 24px;
  width: 564px;
  height: 148px;
  .image {
    float: left;
    position: relative;
    width: 140px;
    height: 140px;
    background-color: #f3f5f7;
    img {
      height: 100%;
      position: absolute;
      bottom: 0;
      border-radius: 8px;
      transform-origin: 50% 100%;
      transition: all .3s;
      &.top {
        transform: translateY(0px);
      }
      &.middle {
        opacity: 0.5;
        transform: scale(0.9) translateY(5px);
      }
      &.bottom {
        opacity: 0.3;
        transform: scale(0.8) translateY(10px);
      }
    }
  }
  h4 {
    margin: 8px 0 8px 164px;
    font-size: 16px;
    color: #1C1F21;
    line-height: 20px;
    min-height: 20px;
    font-weight: bold;
    overflow: hidden;
    text-overflow: ellipsis;
    display: block;
  }
  p {
    margin-left: 164px;
    font-size: 14px;
    color: #545C63;
    letter-spacing: 0;
    line-height: 20px;
    height: 60px;
    overflow: hidden;
    text-overflow: ellipsis;
    display: block;
  }
  .info {
    margin-left: 164px;
    font-size: 12px;
    color: #9199A1;
    height: 18px;
    line-height: 18px;
    span:last-child {
      margin-left: 4em;
    }
  }
  &:hover {
    .image {
      .top {
        transform: translateY(-8px);
      }
      .middle {
        transform: scale(0.88) translateY(-2px);
      }
      .bottom {
        transform: scale(0.78) translateY(4px);
      }
    }
  }
}
</style>
