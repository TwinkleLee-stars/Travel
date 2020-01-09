<template>
  <div class="container" @click="handleClick">
    <div class="wrapper">
      <swiper :options="swiperOption">
        <swiper-slide v-for="(item,index) in list" :key="index">
          <img class="swiper-img" :src="item">
        </swiper-slide>
        <div class="swiper-pagination" slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CommonGallary',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationClickable: true,
        mousewheelControl: true,
        loop: true,
        autoplay: 1500,
        obeserveParents: true,
        observer: true,
        paginationType: 'fraction'
      }
    }
  },
  methods: {
    handleClick () {
      this.$emit('touch')
    }
  },
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  .container >>> .swiper-pagination
    bottom: -1rem
    color: #fff
  .container >>> .swiper-container
    overflow: visible
  .container >>> img
    width: 100%

  .container
    display: flex
    flex-direction: column
    justify-content: center
    position: fixed
    top: 0
    bottom: 0
    right: 0
    left: 0
    background: #000
    .wrapper
      overflow: visible
      width: 100%
      height: 0
      padding-bottom: 100%
</style>
