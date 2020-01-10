<template>
  <div>
    <router-link to="/" tag="div" class="back-icon-wrapper" v-show="!isShow" >
      <span class="iconfont back-icon"> &#xe8b5; </span>
    </router-link>
    <div class="header" v-show="isShow" :style="style">景点详情</div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      isShow: false,
      style: {
        opacity: 1
      }
    }
  },
  methods: {
    changeIsShow () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        this.isShow = true
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity }
      } else {
        this.isShow = false
      }
    }
  },
  mounted () {
    window.addEventListener('scroll', this.changeIsShow)
  },
  unmounted () {
    window.removeEventListener('scroll', this.changeIsShow)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'

  .header
    position: fixed
    top:0
    left:0
    width: 100%
    background-color: $bgColor
    height: $headerHeight
    line-height: $headerHeight
    font-size: .32rem
    color: #fff
    text-align: center

  .back-icon-wrapper
    width: .8rem
    height: .8rem
    border-radius: .4rem
    background: #000
    position: absolute
    top: .2rem
    left: .2rem
    z-index: 99
    .back-icon
      color: #fff;
      position: relative;
      top: .1rem;
      left: .24rem;
      font-size: 0.6rem
</style>
