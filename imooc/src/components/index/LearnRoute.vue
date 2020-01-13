<template>
  <section-tab title="学习路线" :catalog="catalog" more="#">
    <ul v-for="(g, gi) in routeGroups" :key="gi" :slot="'tab-' + (gi + 1)">
      <card v-for="(route, ri) in g.routes" :key="'g_'+gi+'_r_'+ri" :route="route"></card>
    </ul>
  </section-tab>
</template>
<script>
import sectionTab from './SectionTab'
import card from './LearnRouteCard'
export default {
  name: 'LearnRoute',
  components: {
    sectionTab: sectionTab,
    card: card
  },
  data: function () {
    return {
      routeGroups: [
        {
          title: '热门',
          routes: [
            {
              title: 'Go语言从入门到达人之路',
              desc: '零基础入门Go语言，在掌握基础语法后向并发提升，并用Go去构建微服务、上手区块链项目。',
              img: '/static/img/index/route/go.jpg',
              href: '#',
              step: 5,
              lesson: 8,
              favourite: 4112
            },
            {
              title: 'Go语言从入门到达人之路',
              desc: '零基础入门Go语言，在掌握基础语法后向并发提升，并用Go去构建微服务、上手区块链项目。',
              img: '/static/img/index/route/go.jpg',
              href: '#',
              step: 5,
              lesson: 8,
              favourite: 4112
            }
          ]
        },
        {
          title: '前端',
          routes: [
            {
              title: 'Vue.js从入门到全栈开发',
              desc: '优秀的前端工程师都要掌握一门后端语言，从vue到node，前后端通吃，提高前端工程师的竞争力。',
              img: '/static/img/index/route/vue.jpg',
              href: '#',
              step: 4,
              lesson: 5,
              favourite: 11596
            }
          ]
        },
        {
          title: '后端',
          routes: [
            {
              title: '从零开始，实现Python Flask入门到高阶',
              desc: '路线专为零Flask基础的学员定制，我们从Flask最基础的框架开始到多种热门项目实战，层层深入，一站式教程，助你熟练掌握Flask 核心开发。',
              step: 4,
              img: '/static/img/index/route/flask.jpg',
              href: '#',
              lesson: 4,
              favourite: 2751
            },
            {
              title: '从零开始，实现Python Flask入门到高阶',
              desc: '路线专为零Flask基础的学员定制，我们从Flask最基础的框架开始到多种热门项目实战，层层深入，一站式教程，助你熟练掌握Flask 核心开发。',
              step: 4,
              img: '/static/img/index/route/flask.jpg',
              href: '#',
              lesson: 4,
              favourite: 2751
            },
            {
              title: '从零开始，实现Python Flask入门到高阶',
              desc: '路线专为零Flask基础的学员定制，我们从Flask最基础的框架开始到多种热门项目实战，层层深入，一站式教程，助你熟练掌握Flask 核心开发。',
              step: 4,
              img: '/static/img/index/route/flask.jpg',
              href: '#',
              lesson: 4,
              favourite: 2751
            }
          ]
        },
        {
          title: '移动端',
          routes: [
            {
              title: 'Vue.js从入门到全栈开发',
              desc: '优秀的前端工程师都要掌握一门后端语言，从vue到node，前后端通吃，提高前端工程师的竞争力。',
              img: '/static/img/index/route/vue.jpg',
              href: '#',
              step: 4,
              lesson: 5,
              favourite: 11596
            },
            {
              title: 'Vue.js从入门到全栈开发',
              desc: '优秀的前端工程师都要掌握一门后端语言，从vue到node，前后端通吃，提高前端工程师的竞争力。',
              img: '/static/img/index/route/vue.jpg',
              href: '#',
              step: 4,
              lesson: 5,
              favourite: 11596
            },
            {
              title: 'Vue.js从入门到全栈开发',
              desc: '优秀的前端工程师都要掌握一门后端语言，从vue到node，前后端通吃，提高前端工程师的竞争力。',
              img: '/static/img/index/route/vue.jpg',
              href: '#',
              step: 4,
              lesson: 5,
              favourite: 11596
            },
            {
              title: 'Vue.js从入门到全栈开发',
              desc: '优秀的前端工程师都要掌握一门后端语言，从vue到node，前后端通吃，提高前端工程师的竞争力。',
              img: '/static/img/index/route/vue.jpg',
              href: '#',
              step: 4,
              lesson: 5,
              favourite: 11596
            }
          ]
        },
        {
          title: '计算机基础',
          routes: [
            {
              title: 'Go语言从入门到达人之路',
              desc: '零基础入门Go语言，在掌握基础语法后向并发提升，并用Go去构建微服务、上手区块链项目。',
              img: '/static/img/index/route/go.jpg',
              href: '#',
              step: 5,
              lesson: 8,
              favourite: 4112
            }
          ]
        },
        {
          title: '大数据',
          routes: [
            {
              title: '从零开始，实现Python Flask入门到高阶',
              desc: '路线专为零Flask基础的学员定制，我们从Flask最基础的框架开始到多种热门项目实战，层层深入，一站式教程，助你熟练掌握Flask 核心开发。',
              step: 4,
              img: '/static/img/index/route/flask.jpg',
              href: '#',
              lesson: 4,
              favourite: 2751
            },
            {
              title: '从零开始，实现Python Flask入门到高阶',
              desc: '路线专为零Flask基础的学员定制，我们从Flask最基础的框架开始到多种热门项目实战，层层深入，一站式教程，助你熟练掌握Flask 核心开发。',
              step: 4,
              img: '/static/img/index/route/flask.jpg',
              href: '#',
              lesson: 4,
              favourite: 2751
            }
          ]
        },
        {
          title: '测试',
          routes: [
            {
              title: 'Vue.js从入门到全栈开发',
              desc: '优秀的前端工程师都要掌握一门后端语言，从vue到node，前后端通吃，提高前端工程师的竞争力。',
              img: '/static/img/index/route/vue.jpg',
              href: '#',
              step: 4,
              lesson: 5,
              favourite: 11596
            },
            {
              title: 'Vue.js从入门到全栈开发',
              desc: '优秀的前端工程师都要掌握一门后端语言，从vue到node，前后端通吃，提高前端工程师的竞争力。',
              img: '/static/img/index/route/vue.jpg',
              href: '#',
              step: 4,
              lesson: 5,
              favourite: 11596
            }
          ]
        },
        {
          title: '人工智能',
          routes: [
            {
              title: '从零开始，实现Python Flask入门到高阶',
              desc: '路线专为零Flask基础的学员定制，我们从Flask最基础的框架开始到多种热门项目实战，层层深入，一站式教程，助你熟练掌握Flask 核心开发。',
              step: 4,
              img: '/static/img/index/route/flask.jpg',
              href: '#',
              lesson: 4,
              favourite: 2751
            },
            {
              title: '从零开始，实现Python Flask入门到高阶',
              desc: '路线专为零Flask基础的学员定制，我们从Flask最基础的框架开始到多种热门项目实战，层层深入，一站式教程，助你熟练掌握Flask 核心开发。',
              step: 4,
              img: '/static/img/index/route/flask.jpg',
              href: '#',
              lesson: 4,
              favourite: 2751
            }
          ]
        }
      ]
    }
  },
  computed: {
    catalog: function () {
      let arr = []
      this.routeGroups.forEach((item) => {
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
  li {
    list-style: none;
  }
</style>
