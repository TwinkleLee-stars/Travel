<template>
<div>
  <swiper :options="swiperOption">
      <swiper-slide class="icons" v-for="(page,index) in pages" :key="index">
        <div class="icon" v-for="item in page" :key="item.id">
          <div class="icon-img-wrapper">
            <img class="icon-img" :src="item.url"/>
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
  </swiper>
</div>
</template>

<script>
export default{
  name: 'HomeIcons',
  data () {
    return {
      swiperOption: {
        mousewheelControl: true
      },
      iconList: [{
        id: '0001',
        url: 'https://s.qunarzz.com/homenode/images/touchheader/innBnb.png',
        desc: '民宿客栈'
      }, {
        id: '0002',
        url: 'https://s.qunarzz.com/homenode/images/touchheader/bargainflight.png',
        desc: '低价机票'
      }, {
        id: '0003',
        url: 'https://s.qunarzz.com/homenode/images/touchheader/group.png',
        desc: '特惠酒店'
      }, {
        id: '0004',
        url: 'https://s.qunarzz.com/homenode/images/touchheader/haiwai.png',
        desc: '海外酒店'
      }, {id: '0005',
        url: 'https://s.qunarzz.com/homenode/images/touchheader/innBnb.png',
        desc: '民宿客栈'
      }, {
        id: '0006',
        url: 'https://s.qunarzz.com/homenode/images/touchheader/bargainflight.png',
        desc: '低价机票'
      }, {
        id: '0007',
        url: 'https://s.qunarzz.com/homenode/images/touchheader/group.png',
        desc: '特惠酒店'
      }, {
        id: '0008',
        url: 'https://s.qunarzz.com/homenode/images/touchheader/haiwai.png',
        desc: '海外酒店'
      }, {
        id: '0009',
        url: 'https://picbed.qunarzz.com/7804b43ac02cd0333bd0f866eebd43b3.png',
        desc: '一日游'
      }]
    }
  },
  computed: {
    pages () {
      var pages = []
      var page
      this.iconList.forEach((value, index) => {
        page = Math.floor(index / 8)
        if (pages[page] == null) {
          pages[page] = []
        }
        pages[page].push(value)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixin.styl'
  .icons
    width: 100%;
    height: 0;
    padding-bottom: 50%;
    overflow: hidden;
    .icon
      position: relative;
      width: 25%;
      height: 0;
      padding-bottom: 25%;
      overflow: hidden;
      float: left;
      .icon-img-wrapper
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom: .44rem;
        text-align: center;
        .icon-img
          width: 70%;
      .icon-desc
        position: absolute;
        left: 0;
        right: 0;
        text-align: center;
        bottom: .22rem;
        ellipsis();
</style>
