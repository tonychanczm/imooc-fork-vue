<template>
  <section>
    <div class="section-title">
      <h2><slot name="title">{{title}}</slot></h2>
      <ul class="tab-menu">
        <li v-for="(c, ci) in catalog" :key="ci" :class="ci+1 === currentIndex ? 'active':''" @click="currentIndex = ci+1">{{c}}</li>
      </ul>
      <a :href="more" class="more" v-if="more !== undefined">查看更多 <i class="imv2-right2"></i></a>
    </div>
    <div v-for="i in catalog.length" :key="i" v-show="currentIndex === i" class="container">
      <slot :name="'tab-'+i"></slot>
    </div>
  </section>
</template>

<script>
export default {
  name: 'SectionTab',
  props: {
    title: String,
    catalog: Array,
    more: String
  },
  data: function () {
    return {
      currentIndex: 1
    }
  }
}
</script>

<style lang="scss" scoped>
.tab-menu {
  float: left;
  margin-left: 36px;
  li {
    margin: 0 14px;
    float: left;
    font-size: 14px;
    letter-spacing: 0;
    cursor: pointer;
    color: #545C63;
    &.active {
      color: #F20D0D;
      border-bottom: 2px solid #F20D0D;
    }
  }
}
</style>
