<template>
  <div class="list">
    <div class="area">
      <div class="title border-topbottom">当前城市</div>
      <div class="button-list">
        <div class="button-wrapper">
          <div class="button">苏州</div>
        </div>
      </div>
    </div>
    <div class="area">
      <div class="title border-topbottom">热门城市</div>
      <div class="button-list">
        <div class="button-wrapper">
          <div class="button">苏州</div>
        </div>
        <div class="button-wrapper">
          <div class="button">苏州</div>
        </div>
        <div class="button-wrapper">
          <div class="button">苏州</div>
        </div>
        <div class="button-wrapper">
          <div class="button">苏州</div>
        </div>
        <div class="button-wrapper">
          <div class="button">苏州</div>
        </div>
      </div>
    </div>
    <div class="area">
      <div class="title border-topbottom">A</div>
      <div class="item-list">
        <div class="item border-bottom">阿拉尔</div>
        <div class="item border-bottom">阿拉尔</div>
        <div class="item border-bottom">阿拉尔</div>
        <div class="item border-bottom">阿拉尔</div>
        <div class="item border-bottom">阿拉尔</div>
        <div class="item border-bottom">阿拉尔</div>
      </div>
    </div>
  </div>
</template>

<script>
export default{
  name: 'CityList'
}
</script>

<style lang="stylus" scoped>
  .border-topbottom
    &:before
      border-color: #ccc
    &:after
      border-color: #ccc
  .border-bottom
    &:before
      border-color: #ccc
  .list
    overflow: hidden
    position: absolute
    top: 1.77rem
    left: 0
    right: 0
    bottom: 0  
    .title
      line-height: .54rem
      background-color: #eee
      padding-left: .2rem
      color: #666
      font-size: .26rem
    .button-list
      padding: .1rem .6rem .1rem .1rem
      overflow: hidden
      .button-wrapper
        width: 33.33%
        float: left
        .button
          border: #ccc solid .02rem
          border-radius: .06rem
          text-align: center
          margin: .1rem
          padding: .1rem 0
    .item
      line-height: .76rem
      padding-left: .2rem
</style>
