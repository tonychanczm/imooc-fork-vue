<template>
  <section-tab title="热门课程" :catalog="catalog">
    <template v-for="(g, gi) in lessonGroups" :slot="'tab-' + (gi + 1)">
      <card v-for="(lesson, li) in g.lessons" :key="'g_'+gi+'_r_'+li" :lesson="lesson"></card>
    </template>
  </section-tab>
</template>
<script>
import sectionTab from './SectionTab'
import card from '../utils/LessonCard'
export default {
  name: 'LearnRoute',
  components: {
    sectionTab: sectionTab,
    card: card
  },
  data: function () {
    return {
      lessonGroups: [
        {
          title: '实战课程',
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
            },
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
              ],
              sticker: 'upgrade'
            }
          ]
        },
        {
          title: '免费课程',
          lessons: [
            {
              title: 'Java入门第一季',
              level: '初级',
              popularity: 109271,
              img: '/static/img/index/lessons/java.jpg',
              href: '#',
              labels: [
                'Java'
              ],
              desc: '本教程从Java环境搭建、工具使用、基础语法开始，带你入门'
            },
            {
              title: '初识Python',
              level: '初级',
              popularity: 291831,
              img: '/static/img/index/lessons/python.jpg',
              href: '#',
              labels: [
                'Python'
              ],
              desc: '本教程从Python环境搭建、工具使用、基础语法开始，带你入门'
            }
          ]
        }
      ]
    }
  },
  computed: {
    catalog: function () {
      let arr = []
      this.lessonGroups.forEach((item) => {
        arr.push(item.title)
      })
      return arr
    }
  }
}
</script>

<style lang="scss" scoped>

</style>

<style lang="scss">
  .container {
    width: calc(100% + 24px);
    margin-left: -24px;
    overflow: visible;
  }
</style>
