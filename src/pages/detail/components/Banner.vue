<template>
  <div>
    <div class="banner" @click="handleWrapperClick">
      <img class="banner-img" :src="bannerImg">
      <div class="img-info">
        <div class="info-title">{{ sightName }}</div>
        <div class="info-number">
          <span class="info-icon"></span>
          39
        </div>
      </div>
    </div>
    <common-gallary :list="gallaryImgs" @touch="handleContainerClick" v-show="showContainer"></common-gallary>
  </div>
</template>

<script>
import CommonGallary from 'common/Gallary'
export default {
  name: 'DetailBanner',
  components: {
    CommonGallary
  },
  data () {
    return {
      showContainer: false,
      imgs: [
        'http://img1.qunarzz.com/sight/source/1505/9e/21df651e19af5d.jpg_r_640x214_3ea5bb38.jpg',
        'http://img1.qunarzz.com/sight/source/1505/9e/21df651e19af5d.jpg_r_640x214_3ea5bb38.jpg'
      ]
    }
  },
  props: {
    sightName: String,
    bannerImg: String,
    gallaryImgs: Array
  },
  methods: {
    handleWrapperClick () {
      this.showContainer = true
    },
    handleContainerClick () {
      this.showContainer = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  .container swiper >>> swiper-slide
    bottom : -1rem
    color: #fff
  .banner
    position: relative
    height: 0
    padding-bottom: 55%
    overflow: hidden
    img
      width: 100%
    .img-info
      padding: 0 .12rem .12rem .12rem
      color: #fff
      position: absolute
      left: 0
      right: 0
      bottom: 0
      display: flex
      .info-title
        flex: 1

  .container
    position: absolute
    top: 0
    bottom: 0
    left: 0
    right: 0
    background: #000

</style>
