<template>
  <div class="wrapper">
    <swiper :options="swiperOption" :not-next-tick="notNextTick">
      <swiper-slide v-for="item in imgList" :key="item.id">
        <img class="swiper-img" :src="item.url"/>
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default{
  name: 'HomeSwiper',
  data () {
    return {
      notNextTick: true,
      swiperOption: {
        autoplay: 1500,
        pagination: '.swiper-pagination',
        paginationClickable: true,
        mousewheelControl: true,
        loop: true
      },
      imgList: [
        {
          id: '001',
          url: 'https://imgs.qunarzz.com/p/p93/1409/28/a2610215e626d99affffffffc8d65eac.jpg_256x160_1210af41.jpg'
        },
        {
          id: '002',
          url: 'https://imgs.qunarzz.com/p/p29/201302/28/3d20251a1b60350a93835fbb.jpg_256x160_e8f468b0.jpg'
        },
        {
          id: '003',
          url: 'https://imgs.qunarzz.com/p/p73/1504/ab/15bbdcb31d3e61.jpg_256x160_139e3d4e.jpg'
        },
        {
          id: '004',
          url: 'https://imgs.qunarzz.com/p/p48/201302/28/bc44faa497db0dcf93835fbb.jpg_256x160_0ba13461.jpg'
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper>>>.swiper-pagination-bullet-active
    background-color: #fff;
  .wrapper>>>.swiper-pagination-bullet
    background-color: #eff
  .wrapper
    overflow: hidden;
    width: 100%;
    height: 0;
    padding-bottom: 40%;
    .swiper-img
      width: 100%;
      height: 3rem;
</style>
