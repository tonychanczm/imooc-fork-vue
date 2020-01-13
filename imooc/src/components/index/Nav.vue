<template>
  <nav class="nav-bar">
    <h1 class="logo">
      <a href="#"><img src="/static/img/logo.png"/></a>
    </h1>
    <ul class="links">
      <li>
        <a href="#">免费课程</a>
      </li>
      <li>
        <a href="#">实战课程</a>
      </li>
      <li>
        <a href="#">就业班</a>
      </li>
      <li>
        <a href="#">专栏</a>
      </li>
      <li>
        <a href="#">猿问</a>
      </li>
      <li>
        <a href="#">手记</a>
      </li>
    </ul>
    <form class="search">
      <input type="text" placeholder="请输入关键字"/>
      <button type="submit" class="submit-btn">
        <i class="icon-search"></i>
      </button>
    </form>
    <div class="right">
      <div class="download">
        <a href="#">下载app</a>
        <div class="panel">
          <h4>慕课网APP - 随时随地学编程</h4>
          <div class="panel-left">
            <img src="/static/img/index/appload.png">
          </div>
          <div class="panel-right">
            <a href="#" class="btn">
              <i class="icon-apple"></i>
              App Store下载
            </a>
            <a href="#" class="btn">
              <i class="icon-android"></i>
              Android下载
            </a>
            <p>扫描下载慕课网APP</p>
          </div>
        </div>
      </div>
      <div class="cart">
        <a href="#"><i class="icon-shopping-cart"></i> 购物车</a>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Nav'
}
</script>

<style lang="scss" scoped>
  .nav-bar {
    box-shadow: 0 -1px 10px #6f6f6f;
    position: fixed;
    top: 0;
    background-color: #ffffff;
    width: 100vw;
    height: 72px;
    font-size: 16px;
    line-height: 72px;
    z-index: 20;
    color: #424850;
    .logo {
      float: left;
      margin-left: 20px;
      img {
        height: 72px;
      }
    }
    .links {
      float: left;
      li {
        float: left;
        margin-right: 40px;
        a {
          color: #424850;
        }
        &:hover {
          a {
            color: #000;
          }
        }
      }
    }
    .search {
      float: left;
      width: 300px;
      position: relative;
      input {
        height: 40px;
        width: 280px;
        padding: 0 10px;
        font-size: 14px;
        line-height: 40px;
        color: #959595;
        background-color: #e4e4e4;
        border-radius: 6px;
        border: none;
        &::-webkit-input-placeholder {
          color: #959595;
        }
        &:-moz-placeholder {/* Firefox 18- */
          color: #959595;
        }
        &::-moz-placeholder{/* Firefox 19+ */
          color: #959595;
        }
        &:-ms-input-placeholder {
          color: #959595;
        }
      }
      .submit-btn {
        height: 40px;
        width: 40px;
        position: absolute;
        right: 0px;
        font-size: 20px;
        top: 18px;
        border: none;
        background: none;
        cursor: pointer;
      }
    }
    .right {
      float: right;
      font-size: 14px;
      line-height: 72px;
      .download {
        float: left;
        position: relative;
        margin-right: 20px;
        a {
          color: #5e646a;
          &:hover {
            color: red;
          }
        }
        .panel {
          text-align: center;
          padding: 10px 24px 22px;
          position: absolute;
          width: 256px;
          height: auto;
          right: 0;
          background: #fff;
          box-shadow: 0 0 5px #d3dde7;
          border-bottom-left-radius: 8px;
          border-bottom-right-radius: 8px;
          overflow: hidden;
          h4 {
            margin-top: 10px;
            font-size: 14px;
            font-weight: 400;
            line-height: 14px;
            margin-bottom: 10px;
          }
          .panel-left {
            height: 108px;
            img {
              width: 108px;
            }
            float: left;
          }
          .panel-right {
            float: left;
            .btn {
              margin-left: 10px;
              margin-bottom: 10px;
              padding-left: 10px;
              text-align: left;
              display: block;
              width: 122px;
              line-height: 36px;
              height: 36px;
              border-radius: 18px;
              color: #fff;
              background-color: #3d434a;
              &:hover {
                background-color: #000;
              }
            }
            p {
              font-size: 12px;
              margin-top: 12px;
              margin-left: 10px;
              text-align: center;
              line-height: 12px;
            }
          }
          visibility: hidden;
        }
        &:hover {
          .panel {
            visibility: visible;
          }
        }
      }
      .cart {
        float: left;
        position: relative;
        margin-right: 20px;
        a {
          color: #5e646a;
          display: inline-block;
          height: 34px;
          padding: 0 20px;
          line-height: 34px;
          vertical-align: center;
          border-radius: 17px;
          border: solid 1px #d1d7dc;
          &:hover {
            color: red;
          }
        }
      }
    }
  }
</style>
