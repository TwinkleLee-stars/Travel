<template>
  <div>
    <div  v-for="(item,index) in list" :key="index">
      <div class="outer border-bottom">
        <span class="item-icon"></span>
        {{item.title}}
      </div>
      <div class="inner">
        <detail-list v-if="item.children" :list="item.children"></detail-list>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailList',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  .outer
    padding: .2rem 0 0 .2rem
    .item-icon
      position: relative
      left: .06rem
      top: .06rem
      display: inline-block
      width: .36rem
      height: .36rem
      background: url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat
      margin-right: .1rem
      background-size: .4rem 3rem
  .inner
    padding-left: .2rem
</style>
