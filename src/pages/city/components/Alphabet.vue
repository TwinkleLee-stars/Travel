<template>
  <div class="list">
    <div class="item">A</div>
    <div class="item">A</div>
    <div class="item">A</div>
    <div class="item">A</div>
    <div class="item">A</div>
    <div class="item">A</div>
    <div class="item">A</div>
    <div class="item">A</div>
  </div>
</template>

<script>
export default{
  name: 'CityAlphabet'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  
  .list
    position: absolute
    right: 0
    top: 1.77rem
    bottom: 0
    width: .4rem
    display: flex
    flex-direction: column
    justify-content: center
  .item
    text-align: center
    line-height: .4rem
    color: $bgColor
</style>
