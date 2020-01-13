<template>
  <div class="container" :style="{height: height+'px', width: width+'px'}" @mouseenter="stopAutoSwitch" @mouseleave="startAutoSwitch">
    <ul>
      <transition-group name="fade">
        <li v-for="(pic, index) in pics" :key="'pic_'+index" v-show="currentIndex === index">
          <a :href="pic.href">
            <img :src="pic.src" :alt="pic.desc"/>
          </a>
        </li>
      </transition-group>
    </ul>
    <a class="btn-prev icon-left2" @click="prevPic()"></a>
    <a class="btn-next icon-right2" @click="nextPic()"></a>
    <ul class="catalog">
      <li v-for="(_, index) in pics" :key="index" :class="currentIndex === index ? 'active' : ''" @click="switchToNthPic(index)"></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Carousel',
  data: () => {
    return {
      currentIndex: 0,
      interval: null
    }
  },
  props: {
    pics: Array,
    width: Number,
    height: Number
  },
  methods: {
    nextPic: function (auto = false) {
      if (!auto) {
        this.stopAutoSwitch()
      }
      if (this.currentIndex + 1 >= this.pics.length) {
        this.currentIndex = 0
      } else {
        this.currentIndex++
      }
      if (!auto) {
        this.startAutoSwitch()
      }
    },
    prevPic: function () {
      this.stopAutoSwitch()
      if (this.currentIndex <= 0) {
        this.currentIndex = this.pics.length - 1
      } else {
        this.currentIndex--
      }
      this.startAutoSwitch()
    },
    switchToNthPic (n) {
      this.stopAutoSwitch()
      this.currentIndex = n
      this.startAutoSwitch()
    },
    startAutoSwitch: function () {
      this.stopAutoSwitch()
      this.interval = setInterval(function () {
        this.nextPic(true)
      }.bind(this), 3000)
    },
    stopAutoSwitch: function () {
      if (this.interval != null) {
        clearInterval(this.interval)
      }
    }
  },
  mounted: function () {
    console.log(this.height)
    this.startAutoSwitch()
  },
  beforeDestroy: function () {
    this.stopAutoSwitch()
  }
}
</script>

<style lang="scss" scoped>
  .fade-enter-active {
    transition: all .3s;
    z-index: 9;
  }
  .fade-leave-active {
    transition: all .299s;
    z-index: 0;
  }
  .fade-enter /* .fade-leave-active below version 2.1.8 */ {
    opacity: 0;
    z-index: 9;
  }
  .fade-leave-to {
    z-index: 0;
  }

  .container {
    position: relative;
    li {
      position: absolute;
      width: 100%;
      img {
        width: 100%;
        height: auto;
        z-index: 8;
      }
    }
  }

  .btn-prev, .btn-next {
    z-index: 10;
    padding: 0;
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    width: 48px;
    height: 48px;
    border-radius: 50%;
    border-color: transparent;
    background: rgba(0,0,0,0.25);
    color: #fff;
    font-size: 32px;
    line-height: 48px;
    text-align: center;
    text-decoration: none;
    &:hover {
      background: rgba(0,0,0,0.35);
    }
    cursor: pointer;
  }
  .btn-prev {
    left: 16px;
  }
  .btn-next {
    right: 16px;
  }

  .catalog {
    z-index: 10;
    position: absolute;
    bottom: 21px;
    right: 24px;
    overflow: hidden;
    li {
      position: relative;
      width: 8px;
      height: 8px;
      margin-left: 8px;
      float: left;
      background: #fff;
      opacity: 0.8;
      transition: all ease .3s;
      border-radius: 4px;
      cursor: pointer;
      &:hover {
        opacity: 0.9;
      }
    }

    .active {
      width: 20px;
    }
  }
</style>
