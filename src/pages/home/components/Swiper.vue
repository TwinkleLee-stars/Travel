<template>
  <div class="wrapper">
    <swiper :options="swiperOption" :not-next-tick="notNextTick">
      <swiper-slide v-for="item in list" :key="item.id">
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
      }
    }
  },
  props: {
    list: Array
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
