<template>
  <ul class="container">
    <card v-for="(l, li) in lessons" :key="li" :lesson="l"></card>
  </ul>
</template>
<script>
import card from '../utils/LessonCard'
export default {
  name: 'NewLessons',
  components: {
    card: card
  },
  data: function () {
    return {
      lessons: [
        {
          title: 'Go读书社区web开发与高性能架构优化',
          level: '中级',
          popularity: 98,
          comment: 8,
          price: '299.00',
          img: '/static/img/index/lessons/1.jpg',
          href: '#',
          labels: [
            'Nginx', 'Redis'
          ]
        },
        {
          title: '玩转Java并发工具，精通JUC，成为并发多面手',
          level: '中级',
          popularity: 236,
          comment: 19,
          price: '339.00',
          img: '/static/img/index/lessons/2.jpg',
          href: '#',
          sticker: 'new',
          sales: true
        },
        {
          title: 'Vue Element+Node.js开发企业通用管理后台系统',
          level: '高级',
          popularity: 662,
          comment: 15,
          price: '348.00',
          img: '/static/img/index/lessons/3.jpg',
          href: '#',
          labels: [
            'Node.js', 'Vue.js'
          ],
          sticker: 'hot'
        },
        {
          title: '全面系统python3入门+进阶 小白也能听懂 (万人甄选口碑好课)',
          level: '初级',
          popularity: 10267,
          comment: 3664,
          price: '366.00',
          img: '/static/img/index/lessons/4.jpg',
          href: '#',
          labels: [
            'Python'
          ],
          sticker: 'hot'
        },
        {
          title: '全流程开发 TP6.0实战高并发电商服务系统',
          level: '中级',
          popularity: 254,
          comment: 19,
          price: '339.00',
          img: '/static/img/index/lessons/5.jpg',
          href: '#',
          labels: [
            'PHP'
          ],
          sticker: 'new',
          sales: true
        },
        {
          title: 'Java项目面试实操 提升大厂面试成功率',
          level: '初级',
          popularity: 41,
          comment: 4,
          price: '359.00',
          img: '/static/img/index/lessons/6.png',
          href: '#',
          labels: [
            '小程序', 'SSM'
          ],
          sticker: 'new',
          sales: true
        },
        {
          title: '零基础学测试-从入门到就业',
          level: '初级',
          popularity: 59,
          comment: 1,
          price: '348.00',
          img: '/static/img/index/lessons/7.jpg',
          href: '#',
          labels: [
            '功能测试'
          ],
          sticker: 'new',
          sales: true
        },
        {
          title: '编程必备基础 计算机组成原理+操作系统+计算机网络',
          level: '中级',
          popularity: 3011,
          comment: 1051,
          price: '236.00',
          img: '/static/img/index/lessons/8.jpg',
          href: '#',
          labels: [
            'Linux', '计算机网络'
          ],
          sticker: 'hot'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
  .container {
    width: calc(100% + 24px);
    margin-left: -24px;
    overflow: hidden;
  }
</style>
