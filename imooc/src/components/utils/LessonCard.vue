<template>
  <li class="card">
    <a :href="lesson.href">
      <div v-if="lesson.sticker === 'new'" class="sticker new">新课</div>
      <div v-if="lesson.sticker === 'hot'" class="sticker hot">热门</div>
      <div v-if="lesson.sticker === 'upgrade'" class="sticker upgrade">升级</div>
      <div class="image">
        <img :src="lesson.img"/>
        <div v-if="lesson.labels !== undefined" class="labels">
          <label v-for="(ll, lli) in lesson.labels" :key="lli">{{ll}}</label>
        </div>
      </div>
      <div class="content">
        <h3 class="title">
          {{lesson.title}}
        </h3>
        <div class="lesson-info">
          <span>{{lesson.level}}</span>
          <span><i class="imv2-set-sns"></i>{{lesson.popularity}}</span>
          <span class="right" v-if="lesson.comment !== undefined">{{lesson.comment}}人评价</span>
        </div>
        <div class="lesson-price" v-if="lesson.price !== undefined" :class="lesson.sales === true ? 'sales' : ''">¥{{lesson.price}} <span>限时促销</span></div>
        <p class="desc" v-if="lesson.desc !== undefined">{{lesson.desc}}</p>
      </div>
    </a>
  </li>
</template>

<script>
export default {
  name: 'LessonCard',
  props: {
    lesson: Object
  }
}
</script>

<style lang="scss" scoped>
  .card {
    float: left;
    width: 270px;
    height: 268px;
    margin-left: 24px;
    margin-bottom: 12px;
    position: relative;
    a {
      .sticker {
        position: absolute;
        border: 2px solid #FFFFFF;
        border-radius: 12px;
        top: 8px;
        left: -8px;
        z-index: 4;
        font-size: 12px;
        color: #FFFFFF;
        line-height: 20px;
        padding: 0 8px;
        &.new {
          background: #FFAA00 linear-gradient(90deg, #ffaa00 17%, #f76b1c 100%);
        }
        &.hot {
          background: #F02930 linear-gradient(90deg, #f68688 0%, #f02930 100%);
        }
        &.upgrade {
          background: #9447EB linear-gradient(90deg, #bd89f8 6%, #9447eb 93%);
        }
      }
      .image {
        width: 270px;
        height: 148px;
        overflow: hidden;
        position: relative;
        border-radius: 8px;
        img {
          width: 100%;
        }
        .labels {
          position: absolute;
          bottom: 6px;
          left: 8px;
          font-size: 12px;
          color: #FFFFFF;
          line-height: 16px;
          label {
            display: inline-block;
            background: rgba(28, 31, 33, 0.6);
            border-radius: 4px;
            padding: 4px 8px;
            margin-right: 4px;
            margin-bottom: 2px;
            font-weight: 200;
            &:last-child {
              margin-right: 0;
            }
          }
        }
      }
      .content {
        padding: 8px;
        .title {
          font-size: 16px;
          color: #07111B;
          line-height: 24px;
          word-wrap: break-word;
          overflow: hidden;
          text-overflow: ellipsis;
          display: -webkit-box;
          -webkit-line-clamp: 2;
          -webkit-box-orient: vertical;
          transition: all .3s;
          font-weight: bold;
          height: 46px;
          transition: color ease .3s;
        }
        .lesson-info {
          font-size: 12px;
          color: #9199A1;
          font-weight: 400;
          line-height: 18px;
          margin-top: 4px;
          span {
            display: inline-block;
            margin-right: 12px;
            &.right {
              float: right;
            }
          }
        }
        .lesson-price {
          line-height: 16px;
          font-size: 12px;
          color: #545C63;
          &.sales {
            color: #F01414 !important;
            font-weight: bold;
            span {
              visibility: visible !important;
            }
          }
          span {
            box-sizing: border-box;
            background: rgba(242, 13, 13, 0.08);
            border-radius: 2px;
            font-weight: 200;
            color: #F20D0D;
            padding: 0 4px;
            display: inline-block;
            visibility: hidden;
          }
        }
        .desc {
          font-size: 12px;
          color: #9199A1;
          font-weight: 400;
          line-height: 18px;
          margin-top: 4px;
          overflow: hidden;
          text-overflow: ellipsis;
          width: 253px;
          display: -webkit-box;
        }
      }
      &:hover {
        .title {
          color: #ff0000;
        }
      }
    }
  }
</style>
