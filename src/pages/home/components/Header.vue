<template>
  <div class="header">
    <div class="header-left"><span class="iconfont back-icon"> &#xe8b5; </span></div>
    <div class="header-input"><span class="iconfont">&#xe86e;</span>输入城市/景点/游玩主题</div>
    <router-link to="/city">
      <div class="header-right">{{city}}<span class="iconfont">&#xe649;</span></div>
    </router-link>
  </div>
</template>

<script>
export default{
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    display: flex;
    line-height: .86rem;
    color: #fff;
    background-color: $bcColor;
    .header-left
      width: .64rem;
      float: left;
      .back-icon
        display: block;
        font-size: .4rem;
        text-align: center;
        padding-left: .3rem;
    .header-input
      flex: 1;
      border-radius: .1rem;
      color: #ccc;
      background-color: #fff;
      margin-top: .12rem;
      margin-left: .2rem;
      height: .62rem;
      line-height: .62rem;
      padding-left: .2rem;
    .header-right
      width: 1.24rem;
      float: right;
      text-align: center;
      color: #fff;
</style>
