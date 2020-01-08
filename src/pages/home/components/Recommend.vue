<template>
  <div class="recommend">
    <div class="title">热销推荐</div>
    <router-link :to="'/detail/'+item.id"
      tag="li"
      class="item border-bottom"
      v-for="item in list"
      :key="item.id">
      <img class="item-img" :src="item.url"/>
      <div class="item-info">
        <p class="item-title">{{item.title}}</p>
        <p class="item-desc">{{item.desc}}</p>
        <button class="item-button">查看详情</button>
      </div>
    </router-link>
  </div>
</template>

<script>
export default{
  name: 'HomeRecommend',
  data () {
    return {
    }
  },
  props: {
    list: Array
  }

}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixin.styl'
  .title
    line-height: .8rem;
    text-indent: .2rem;
    background-color: #eee;
    margin-top: .2rem;
  .item
    height: 1.9rem;
    overflow: hidden;
    display: flex;
    .item-img
      padding: .1rem;
      width: 1.7rem;
      height: 1.7rem;
    .item-info
      flex: 1;
      padding: .1rem;
      min-width: 0;
      .item-title
        font-size: .32rem;
        line-height: .54rem;
        ellipsis()
      .item-desc
        line-height: .4rem;
        color: #ccc;
        ellipsis()
      .item-button
        line-height: .44rem;
        margin-top: .16rem;
        background: #ff9300;
        padding: 0 .2rem;
        border-radius: .06rem;
        color: #fff;
</style>
