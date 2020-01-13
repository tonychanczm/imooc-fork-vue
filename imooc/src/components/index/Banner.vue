<template>
<div id="banner">
  <ul class="catalog">
    <li v-for="(c, index) in catalog" :key="'c_'+index" class="catalog-item">
      <span class="group">{{c.title}}</span>
      <i class="imv2-arrow1_r"></i>
      <div class="card" >
        <div v-for="(g, gIndex) in c.card.groups" :key="'g_'+gIndex">
          <h4>{{g.title}}</h4>
          <a class="text-link" v-for="(l, lIndex) in g.links" :key="'gl_'+lIndex" :href="l.href">{{l.title}}</a>
        </div>
        <div>
          <ul class="ad">
            <li class="block" v-for="(ad, aIndex) in c.card.ads" :key="'ad_'+aIndex">
              <a :href="ad.href">
                <img class="img" :src="ad.img" v-if="ad.type === 'lesson'"/>
                <div class="img route" v-if="ad.type === 'route'">
                  <div class="route-img-border up">
                    <img class="route-img" :src="ad.img">
                  </div>
                  <div class="route-img-border mid">
                    <img class="route-img" :src="ad.img">
                  </div>
                  <div class="route-img-border down">
                    <img class="route-img" :src="ad.img">
                  </div>
                </div>
                <h5 class="intro-title">{{ad.title}}</h5>
                <span class="lesson-intro" v-if="ad.type === 'lesson'">
                  <span class="price" :class="ad.specOffer?'special-price':''" v-if="ad.price !== undefined">¥{{ad.price}}
                    <span class="special-offer" v-if="ad.specOffer">限时优惠</span>
                    <span class="dot">·</span>
                  </span>
                  <span class="level">{{ad.level}}</span>
                  <span class="dot">·</span>
                  <span class="popularity"><i class="icon-set_sns"></i>{{ad.popularity}}</span>
                </span>
                <span class="route-intro" v-if="ad.type === 'route'">
                  <span class="path">路线</span>
                  <span class="step">{{ad.step}}步骤</span>
                  <span class="dot">·</span>
                  <span class="lesson">{{ad.lesson}}门课</span>
                  <span class="popularity"><i class="imv2-star2"></i>{{ad.popularity}}人收藏</span>
                </span>
              </a>
            </li>
          </ul>
        </div>
      </div>
    </li>
  </ul>
  <carousel class="carousel" :pics="pics" :width="936" :height="382"></carousel>
</div>
</template>

<script>
import carousel from '../utils/Carousel'
export default {
  name: 'Banner',
  components: {
    carousel: carousel
  },
  data: () => {
    return {
      pics: [
        {
          src: '/static/img/banner/carousel_1.jpg',
          href: '#',
          desc: 'Carousel Demo'
        },
        {
          src: '/static/img/banner/carousel_2.jpg',
          href: '#',
          desc: 'Carousel Demo'
        },
        {
          src: '/static/img/banner/carousel_3.jpg',
          href: '#',
          desc: 'Carousel Demo'
        },
        {
          src: '/static/img/banner/carousel_4.jpg',
          href: '#',
          desc: 'Carousel Demo'
        },
        {
          src: '/static/img/banner/carousel_5.jpg',
          href: '#',
          desc: 'Carousel Demo'
        }
      ],
      catalog: [
        {
          title: '前沿 / 区块链 / 人工智能',
          card: {
            groups: [
              {
                title: '前沿技术',
                links: [
                  {
                    title: '微服务',
                    href: '#'
                  },
                  {
                    title: '区块链',
                    href: '#'
                  },
                  {
                    title: '以太坊',
                    href: '#'
                  },
                  {
                    title: '人工智能',
                    href: '#'
                  },
                  {
                    title: '机器视觉',
                    href: '#'
                  }
                ]
              }
            ],
            ads: [
              {
                type: 'lesson',
                title: 'JavaScript玩转机器学习 打造...',
                img: '/static/img/banner/lesson_1.png',
                href: '#',
                price: '308.00',
                specOffer: true,
                level: '初级',
                popularity: 83
              },
              {
                type: 'lesson',
                title: 'ElasticSearch+Spark 构造高...',
                img: '/static/img/banner/lesson_2.png',
                href: '#',
                price: '348.00',
                level: '中级',
                popularity: 533
              },
              {
                type: 'route',
                title: '从0入门人工智能学习',
                img: '/static/img/banner/route_1.jpg',
                href: '#',
                step: 5,
                lesson: 5,
                popularity: 13761
              },
              {
                type: 'lesson',
                title: '推荐算法理论与实践',
                img: '/static/img/banner/lesson_3.jpg',
                href: '#',
                level: '中级',
                popularity: 16790
              }
            ]
          }
        },
        {
          title: '前沿 / 区块链 / 人工智能',
          card: {
            groups: [
              {
                title: '前沿技术',
                links: [
                  {
                    title: '微服务',
                    href: '#'
                  },
                  {
                    title: '区块链',
                    href: '#'
                  },
                  {
                    title: '以太坊',
                    href: '#'
                  },
                  {
                    title: '人工智能',
                    href: '#'
                  },
                  {
                    title: '机器视觉',
                    href: '#'
                  }
                ]
              }
            ],
            ads: [
              {
                type: 'lesson',
                title: 'JavaScript玩转机器学习 打造...',
                img: '/static/img/banner/lesson_1.png',
                href: '#',
                price: '308.00',
                specOffer: true,
                level: '初级',
                popularity: 83
              },
              {
                type: 'lesson',
                title: 'ElasticSearch+Spark 构造高...',
                img: '/static/img/banner/lesson_2.png',
                href: '#',
                price: '348.00',
                level: '中级',
                popularity: 533
              },
              {
                type: 'route',
                title: '从0入门人工智能学习',
                img: '/static/img/banner/route_1.jpg',
                href: '#',
                step: 5,
                lesson: 5,
                popularity: 13761
              },
              {
                type: 'lesson',
                title: '推荐算法理论与实践',
                img: '/static/img/banner/lesson_3.jpg',
                href: '#',
                level: '中级',
                popularity: 16790
              }
            ]
          }
        },
        {
          title: '前沿 / 区块链 / 人工智能',
          card: {
            groups: [
              {
                title: '前沿技术',
                links: [
                  {
                    title: '微服务',
                    href: '#'
                  },
                  {
                    title: '区块链',
                    href: '#'
                  },
                  {
                    title: '以太坊',
                    href: '#'
                  },
                  {
                    title: '人工智能',
                    href: '#'
                  },
                  {
                    title: '机器视觉',
                    href: '#'
                  }
                ]
              }
            ],
            ads: [
              {
                type: 'lesson',
                title: 'JavaScript玩转机器学习 打造...',
                img: '/static/img/banner/lesson_1.png',
                href: '#',
                price: '308.00',
                specOffer: true,
                level: '初级',
                popularity: 83
              },
              {
                type: 'lesson',
                title: 'ElasticSearch+Spark 构造高...',
                img: '/static/img/banner/lesson_2.png',
                href: '#',
                price: '348.00',
                level: '中级',
                popularity: 533
              },
              {
                type: 'route',
                title: '从0入门人工智能学习',
                img: '/static/img/banner/route_1.jpg',
                href: '#',
                step: 5,
                lesson: 5,
                popularity: 13761
              },
              {
                type: 'lesson',
                title: '推荐算法理论与实践',
                img: '/static/img/banner/lesson_3.jpg',
                href: '#',
                level: '中级',
                popularity: 16790
              }
            ]
          }
        },
        {
          title: '前沿 / 区块链 / 人工智能',
          card: {
            groups: [
              {
                title: '前沿技术',
                links: [
                  {
                    title: '微服务',
                    href: '#'
                  },
                  {
                    title: '区块链',
                    href: '#'
                  },
                  {
                    title: '以太坊',
                    href: '#'
                  },
                  {
                    title: '人工智能',
                    href: '#'
                  },
                  {
                    title: '机器视觉',
                    href: '#'
                  }
                ]
              }
            ],
            ads: [
              {
                type: 'lesson',
                title: 'JavaScript玩转机器学习 打造...',
                img: '/static/img/banner/lesson_1.png',
                href: '#',
                price: '308.00',
                specOffer: true,
                level: '初级',
                popularity: 83
              },
              {
                type: 'lesson',
                title: 'ElasticSearch+Spark 构造高...',
                img: '/static/img/banner/lesson_2.png',
                href: '#',
                price: '348.00',
                level: '中级',
                popularity: 533
              },
              {
                type: 'route',
                title: '从0入门人工智能学习',
                img: '/static/img/banner/route_1.jpg',
                href: '#',
                step: 5,
                lesson: 5,
                popularity: 13761
              },
              {
                type: 'lesson',
                title: '推荐算法理论与实践',
                img: '/static/img/banner/lesson_3.jpg',
                href: '#',
                level: '中级',
                popularity: 16790
              }
            ]
          }
        },
        {
          title: '前沿 / 区块链 / 人工智能',
          card: {
            groups: [
              {
                title: '前沿技术',
                links: [
                  {
                    title: '微服务',
                    href: '#'
                  },
                  {
                    title: '区块链',
                    href: '#'
                  },
                  {
                    title: '以太坊',
                    href: '#'
                  },
                  {
                    title: '人工智能',
                    href: '#'
                  },
                  {
                    title: '机器视觉',
                    href: '#'
                  }
                ]
              }
            ],
            ads: [
              {
                type: 'lesson',
                title: 'JavaScript玩转机器学习 打造...',
                img: '/static/img/banner/lesson_1.png',
                href: '#',
                price: '308.00',
                specOffer: true,
                level: '初级',
                popularity: 83
              },
              {
                type: 'lesson',
                title: 'ElasticSearch+Spark 构造高...',
                img: '/static/img/banner/lesson_2.png',
                href: '#',
                price: '348.00',
                level: '中级',
                popularity: 533
              },
              {
                type: 'route',
                title: '从0入门人工智能学习',
                img: '/static/img/banner/route_1.jpg',
                href: '#',
                step: 5,
                lesson: 5,
                popularity: 13761
              },
              {
                type: 'lesson',
                title: '推荐算法理论与实践',
                img: '/static/img/banner/lesson_3.jpg',
                href: '#',
                level: '中级',
                popularity: 16790
              }
            ]
          }
        },
        {
          title: '前沿 / 区块链 / 人工智能',
          card: {
            groups: [
              {
                title: '前沿技术',
                links: [
                  {
                    title: '微服务',
                    href: '#'
                  },
                  {
                    title: '区块链',
                    href: '#'
                  },
                  {
                    title: '以太坊',
                    href: '#'
                  },
                  {
                    title: '人工智能',
                    href: '#'
                  },
                  {
                    title: '机器视觉',
                    href: '#'
                  }
                ]
              }
            ],
            ads: [
              {
                type: 'lesson',
                title: 'JavaScript玩转机器学习 打造...',
                img: '/static/img/banner/lesson_1.png',
                href: '#',
                price: '308.00',
                specOffer: true,
                level: '初级',
                popularity: 83
              },
              {
                type: 'lesson',
                title: 'ElasticSearch+Spark 构造高...',
                img: '/static/img/banner/lesson_2.png',
                href: '#',
                price: '348.00',
                level: '中级',
                popularity: 533
              },
              {
                type: 'route',
                title: '从0入门人工智能学习',
                img: '/static/img/banner/route_1.jpg',
                href: '#',
                step: 5,
                lesson: 5,
                popularity: 13761
              },
              {
                type: 'lesson',
                title: '推荐算法理论与实践',
                img: '/static/img/banner/lesson_3.jpg',
                href: '#',
                level: '中级',
                popularity: 16790
              }
            ]
          }
        },
        {
          title: '前沿 / 区块链 / 人工智能',
          card: {
            groups: [
              {
                title: '前沿技术',
                links: [
                  {
                    title: '微服务',
                    href: '#'
                  },
                  {
                    title: '区块链',
                    href: '#'
                  },
                  {
                    title: '以太坊',
                    href: '#'
                  },
                  {
                    title: '人工智能',
                    href: '#'
                  },
                  {
                    title: '机器视觉',
                    href: '#'
                  }
                ]
              }
            ],
            ads: [
              {
                type: 'lesson',
                title: 'JavaScript玩转机器学习 打造...',
                img: '/static/img/banner/lesson_1.png',
                href: '#',
                price: '308.00',
                specOffer: true,
                level: '初级',
                popularity: 83
              },
              {
                type: 'lesson',
                title: 'ElasticSearch+Spark 构造高...',
                img: '/static/img/banner/lesson_2.png',
                href: '#',
                price: '348.00',
                level: '中级',
                popularity: 533
              },
              {
                type: 'route',
                title: '从0入门人工智能学习',
                img: '/static/img/banner/route_1.jpg',
                href: '#',
                step: 5,
                lesson: 5,
                popularity: 13761
              },
              {
                type: 'lesson',
                title: '推荐算法理论与实践',
                img: '/static/img/banner/lesson_3.jpg',
                href: '#',
                level: '中级',
                popularity: 16790
              }
            ]
          }
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
  #banner {
    position: relative;
    width: 1152px;
    height: 382px;
    overflow: hidden;
    border-radius: 8px;
    .catalog {
      background-color: #21262d;
      padding: 16px 0 16px 12px;
      height: 350px;
      width: 204px;
      position: absolute;
      z-index: 10;
      .catalog-item {
        border-top-left-radius: 4px;
        border-bottom-left-radius: 4px;
        font-size: 14px;
        font-weight: 400;
        height: 50px;
        line-height: 50px;
        width: 188px;
        padding-left: 16px;
        color: #979a9f;
        .imv2-arrow1_r {
          position: absolute;
          right: 0;
          margin-top: 17px;
          margin-right: 10px;
          font-size: 16px;
        }
        &:hover {
          background-color: #585e62;
          color: #fefefe;
          .card {
            visibility: visible;
          }
        }
        .card {
          line-height: 14px;
          position: absolute;
          left: 216px;
          top: 0;
          width: 694px;
          height: 322px;
          z-index: 9;
          background-color: #ffffff;
          padding: 30px 37px;
          color: #27282a;
          visibility: hidden;
          h4 {
            line-height: 14px;
            font-size: 14px;
            margin-bottom: 20px;
          }
          .text-link {
            margin-bottom: 25px;
            margin-right: 25px;
            display: inline-block;
            color: #27282a;
            &:hover {
              color: #515255;
            }
          }
          .ad {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 732px;
            background-color: #f7f9fb;
            padding: 27px 0 0 36px;
            overflow: hidden;
            .block {
              float: left;
              width: 312px;
              height: 52px;
              margin: 0 48px 27px 0;
              overflow: hidden;
              .img {
                margin-right: 16px;
                float: left;
                border-radius: 4px;
                height: 52px;
                width: auto;
                &.route {
                  width: 52px;
                  position: relative;
                  .route-img-border {
                    border-radius: 4px;
                    height: 52px;
                    width: 52px;
                    position: absolute;
                    overflow: hidden;
                    left: 0;
                    .route-img {
                      height: 52px;
                      width: auto;
                      transform: translateX(-25%);
                      position: absolute;
                      left: 0;
                    }
                  }
                }
              }
              .intro-title {
                font-size: 14px;
                line-height: 22px;
                color: #2c323a;
              }
              white-space: nowrap;
              text-overflow:ellipsis;
              .lesson-intro, .route-intro {
                float: left;
                span {
                  color: #80878f;
                  font-size: 12px;
                  line-height: 18px;
                }
              }
              .dot {
                color: #18191b;
              }
              .lesson-intro {
                .price {
                  font-weight: 900;
                  .special-offer {
                    background-color: #f8e4e6;
                    padding: 0 4px 0 4px;
                    border-radius: 2px;
                    font-weight: 300;
                    color: #ee383f;
                  }
                }
                .special-price {
                  color: #ee383f;
                }
              }
              .route-intro {
                .path {
                  background-color: #ee383f;
                  color: #fff;
                  padding: 0 4px 0 4px;
                  border-radius: 2px;
                  font-weight: 900;

                }
              }
            }
          }
        }
      }
    }
    .carousel {
      position: absolute;
      top: 0;
      right: 0;
      z-index: 8;
    }
  }
</style>
