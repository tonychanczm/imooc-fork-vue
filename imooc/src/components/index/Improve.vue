<template>
  <div class="container">
    <a v-for="(box, i) in boxes" :key="i" :href="box.href" class="box">
      <img :src="box.img"/>
    </a>
  </div>
</template>

<script>
export default {
  name: 'Improve',
  data: function () {
    return {
      boxes: [
        {
          title: '从Java后段到全栈',
          desc: '浓缩七月从工程师到CTO到10年成长历程',
          img: '/static/img/index/box-java1.png',
          href: '#'
        },
        {
          title: '大前端——前端高级进阶',
          desc: '覆盖前端全栈+全周期+多端应用到体系大课',
          img: '/static/img/index/box-fe.png',
          href: '#'
        },
        {
          title: 'Java架构师',
          desc: '跟随千万级项目从0到100一起成长',
          img: '/static/img/index/box-java2.png',
          href: '#'
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
  .box {
    float: left;
    display: block;
    margin-right: 24px;
    width: calc((100% - 2 * 24px) / 3);
    background-size: 100%;
    &:last-child {
      margin-right: 0;
    }
    img {
      width: 100%;
    }
  }
</style>
