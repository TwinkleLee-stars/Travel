<template>
  <div class="header">
    <router-link to="/">
      <div class="iconfont back-icon"> &#xe8b5; </div>
    </router-link>
    城市选择
  </div>
</template>

<script>
export default{
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'

  .header
    position: relative
    background-color: $bgColor
    height: $headerHeight
    line-height: $headerHeight
    font-size: .32rem
    color: #fff
    text-align: center
    .back-icon
      position: absolute
      top: 0
      left: 0
      color:#fff
      font-size: .4rem
      text-align: center
      padding-left: .3rem
</style>
