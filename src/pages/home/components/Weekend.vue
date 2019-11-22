<template>
  <div class="recommend">
    <div class="title">周末去哪儿</div>
    <div class="item border-bottom" v-for="item in list" :key="item.id">
      <div class="item-img-wrapper">
        <img class="item-img" :src="item.url"/>
      </div>
      <div class="item-info">
        <p class="item-title">{{item.title}}</p>
        <p class="item-desc">{{item.desc}}</p>
      </div>
    </div>
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
  .title
    line-height: .8rem;
    text-indent: .2rem;
    background-color: #eee;
  .item-img-wrapper
    overflow: hidden;
    height: 0;
    padding-bottom: 37.09%;
    .item-img
      width: 100%;
  .item-info
    padding: .1rem;
    min-width: 0;
    .item-title
      font-size: .32rem;
      line-height: .54rem;
      ellipsis();
    .item-desc
      line-height: .4rem;
      color: #ccc;
      ellipsis();
</style>
