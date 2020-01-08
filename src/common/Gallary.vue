<template>
  <div class="container">
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
        obeserveParents: true,
        observer: true
      }
    }
  },
  methods: {
    handleClick () {
      this.$emit('touch')
    }
  },
  props: {
    list: {
      type: Array,
      default () {
        return []
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
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
      overflow: hidden
      width: 100%
      height: 0
      padding-bottom: 100%
</style>
