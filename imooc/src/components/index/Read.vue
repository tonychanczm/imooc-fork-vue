<template>
  <ul class="container">
    <li class="card">
      <div class="img">
        <a href="#">
          <img src="/static/img/index/read/book2.jpg"/>
          <div class="preview"><img src="/static/img/index/read/preview.png"/></div>
        </a>
      </div>
      <h4><a href="#">分布式技术面试大厂真题30讲</a></h4>

    </li>
  </ul>
</template>

<script>
export default {
  name: 'Read'
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
  }
</style>
