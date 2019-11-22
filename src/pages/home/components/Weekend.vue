<template>
  <div class="recommend">
    <div class="title">周末去哪儿</div>
    <div class="item border-bottom" v-for="item in itemList" :key="item.id">
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
      itemList: [{
        id: '001',
        url: 'http://img1.qunarzz.com/sight/source/1510/6e/1ea71e2f04e.jpg_r_640x214_aa6f091d.jpg',
        title: '北京温泉排行榜',
        desc: '细数北京温泉，温暖你的冬天'
      }, {
        id: '002',
        url: 'http://img1.qunarzz.com/sight/source/1510/6e/1ea71e2f04e.jpg_r_640x214_aa6f091d.jpg',
        title: '北京温泉排行榜',
        desc: '细数北京温泉，温暖你的冬天'
      }, {
        id: '003',
        url: 'http://img1.qunarzz.com/sight/source/1510/6e/1ea71e2f04e.jpg_r_640x214_aa6f091d.jpg',
        title: '北京温泉排行榜',
        desc: '细数北京温泉，温暖你的冬天'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .title
    line-height: .8rem;
    text-indent: .2rem;
    background-color: #eee;
    margin-top: .2rem;
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
