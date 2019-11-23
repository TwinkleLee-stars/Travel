<template>
  <div class="search">
    <input type="text" class="search-input" placeholder="输入城市名或拼音">
  </div>
</template>

<script>
export default{
  name: 'CitySearch'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'

  .search
    background-color: $bgColor
    height: .72rem
    padding: .1rem
    margin-top: -0.01rem
    .search-input
      box-sizing: border-box
      border-radius: .06rem
      height: .68rem
      line-height: .68rem
      width: 100%
      text-align: center
      color: #666
      padding 0 .1rem
</style>
