<template>
  <div class="header">
    <div class="header-left"><span class="back-icon"> &#xe8b5; </span></div>
    <div class="header-input"><span class="search-icon">&#xe86e;</span>输入城市/景点/游玩主题</div>
    <div class="header-right">城市<span class="arrow-down-icon">&#xe649;</span></div>
  </div>
</template>

<script>
export default{
  name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
  .header
    display: flex;
    line-height: .86rem;
    color: #fff;
    background-color: #00bcd4;
    .header-left
      width: .64rem;
      float: left;
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
</style>
