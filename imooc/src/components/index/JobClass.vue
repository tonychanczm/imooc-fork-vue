<template>
  <div class="container">
    <div class="card" v-for="(card, index) in cards" :key="'card_'+index">
      <div class="img" :style="{backgroundPositionY: -1 * 50*index + 'px'}"></div>
      <div class="text">
        <h3>{{card.title}}</h3>
        <small>{{card.desc}}</small>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'JobClass',
  data: function () {
    return {
      cards: [
        {
          title: 'Web前端工程师',
          desc: '从未接触编程也可以学好'
        },
        {
          title: 'Java工程师',
          desc: '综合就业排名第一'
        },
        {
          title: 'Python工程师',
          desc: '应用领域最广泛'
        },
        {
          title: 'Android工程师',
          desc: '移动市场份额第一'
        },
        {
          title: 'PHP工程师',
          desc: 'Web开发首选语言'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
  .container {
    overflow: hidden;
  }
  .card {
    float: left;
    width: calc((100% - 4 * 18px) / 5);
    margin-right: 18px;
    height: 80px;
    background-color: #f1f2f4;
    border-radius: 6px;
    overflow: hidden;
    &:last-child {
      margin-right: 0;
    }
    .img {
      float: left;
      width: 50px;
      height: 50px;
      background-image: url("/static/img/index/path-2019-9.png");
      background-size: 50px;
      border-radius: 3px;
      position: relative;
      margin-top: 15px;
      margin-left: 12px;
    }
    .text {
      float: left;
      margin-top: 22px;
      margin-left: 10px;
      h3 {
        letter-spacing: 1px;
        font-size: 16px;
        line-height: 16px;
      }
      small {
        display: block;
        font-size: 12px;
        line-height: 12px;
        margin-top: 8px;
      }
    }
  }
</style>
