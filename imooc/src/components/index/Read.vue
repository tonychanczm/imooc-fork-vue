<template>
  <ul class="container">
    <li class="card" v-for="(r, ri) in read" :key="ri">
      <div class="img">
        <a :href="r.href">
          <img :src="r.img"/>
          <div class="preview"><img src="/static/img/index/read/preview.png"/></div>
        </a>
      </div>
      <h4><a :href="r.href">{{r.title}}</a></h4>
      <div class="info">
        <span>共{{r.lesson}}节 · {{r.popularity}}人已购买</span>
      </div>
      <div class="author">
        <a :href="r.authorDesc">
          <span>{{r.author}}</span>
          / {{r.authorDesc}}
        </a>
      </div>
      <div class="price">
        <span class="sale-price">¥ {{r.price}}</span>
        <span class="ori-price">原价 ¥ {{r.oriPrice}}</span>
        <div class="sale" v-if="r.sale === true">限制优惠</div>
      </div>
    </li>
  </ul>
</template>

<script>
export default {
  name: 'Read',
  data: function () {
    return {
      read: [
        {
          title: '分布式技术面试大厂真题30讲',
          img: '/static/img/index/read/book2.jpg',
          href: '#',
          lesson: 30,
          popularity: 175,
          author: '王炸',
          authorDesc: '8年经验一线大厂架构师',
          authorHref: '#',
          price: '45.00',
          oriPrice: '68.00',
          sale: true
        },
        {
          title: '分布式技术面试大厂真题30讲',
          img: '/static/img/index/read/book2.jpg',
          href: '#',
          lesson: 30,
          popularity: 175,
          author: '王炸',
          authorDesc: '8年经验一线大厂架构师',
          authorHref: '#',
          price: '45.00',
          oriPrice: '68.00',
          sale: true
        },
        {
          title: '分布式技术面试大厂真题30讲',
          img: '/static/img/index/read/book2.jpg',
          href: '#',
          lesson: 30,
          popularity: 175,
          author: '王炸',
          authorDesc: '8年经验一线大厂架构师',
          authorHref: '#',
          price: '45.00',
          oriPrice: '68.00',
          sale: true
        },
        {
          title: '分布式技术面试大厂真题30讲',
          img: '/static/img/index/read/book2.jpg',
          href: '#',
          lesson: 30,
          popularity: 175,
          author: '王炸',
          authorDesc: '8年经验一线大厂架构师',
          authorHref: '#',
          price: '45.00',
          oriPrice: '68.00',
          sale: true
        },
        {
          title: '分布式技术面试大厂真题30讲',
          img: '/static/img/index/read/book2.jpg',
          href: '#',
          lesson: 30,
          popularity: 175,
          author: '王炸',
          authorDesc: '8年经验一线大厂架构师',
          authorHref: '#',
          price: '45.00',
          oriPrice: '68.00',
          sale: true
        },
        {
          title: '分布式技术面试大厂真题30讲',
          img: '/static/img/index/read/book2.jpg',
          href: '#',
          lesson: 30,
          popularity: 175,
          author: '王炸',
          authorDesc: '8年经验一线大厂架构师',
          authorHref: '#',
          price: '45.00',
          oriPrice: '68.00',
          sale: true
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
    overflow-y: hidden;
  }
  .card {
    float: left;
    padding: 18px;
    margin-left: 24px;
    margin-bottom: 24px;
    width: 332px;
    height: 174px;
    transition: all .3s;
    &:hover {
      background: #FFFFFF;
      box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.1);
      border-radius: 8px;
    }
    .img {
      float: left;
      position: relative;
      img {
        height: 118px;
        width: 104px;
      }
      .preview {
        img {
          margin-top: 5px;
          width: 30px;
          height: 20px;
        }
      }
    }
    h4 {
      margin-left: 112px;
      font-size: 14px;
      line-height: 22px;
      height: 44px;
      font-weight: bold;
      overflow: hidden;
      text-overflow: ellipsis;
      &:hover {
        color: #37f;
      }
    }
    .info {
      margin-left: 112px;
      padding: 10px 0;
      font-size: 12px;
      color: #9199A1;
      text-align: left;
      line-height: 14px;
      border-bottom: 1px solid rgba(28, 31, 33, 0.1);
    }
    .author {
      margin: 10px 0 10px 112px;
      font-size: 12px;
      color: #1C1F21;
      text-align: left;
      line-height: 16px;
      overflow: hidden;
      height: 16px;
      text-overflow: ellipsis;
      white-space: nowrap;
      span {
        font-weight: bold;
      }
      &:hover {
        color: #f20d0d;
      }
    }
    .price {
      margin-left: 112px;
      margin-top: 17px;
      position: relative;
      .sale-price {
        font-size: 16px;
        color: #3377FF;
        text-align: left;
        line-height: 32px;
        font-weight: bold;
      }
      .ori-price {
        margin-left: 8px;
        font-size: 12px;
        color: #9199A1;
        text-align: left;
        line-height: 30px;
        text-decoration: line-through;
      }
      .sale {
        position: absolute;
        top: 7px;
        right: 0;
        text-align: right;
        color: #fff;
        line-height: 16px;
        height: 16px;
        background-image: linear-gradient(90deg, #3377ff 0, #74ccff 99%);
        padding: 2px 6px;
        font-size: 12px;
      }
    }
  }
</style>
