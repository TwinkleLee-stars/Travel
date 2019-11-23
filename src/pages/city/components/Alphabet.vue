<template>
  <div class="list">
    <div class="item" v-for="key of letters" :key="key" :ref="key"
      @click="handleClick"
      @touchstart="handleTouchStart"
      @touchmove="handleTouchMove"
      @touchend="handleTouchEnd"
    >
      {{key}}
    </div>
  </div>
</template>

<script>
export default{
  name: 'CityAlphabet',
  props: {
    cities: Object
  },
  data () {
    return {
      touchStatus: false,
      startY: 0,
      timer: null
    }
  },
  computed: {
    letters () {
      let letters = []
      for (let i in this.cities) {
        letters.push(i)
      }
      return letters
    }
  },
  methods: {
    handleClick (e) {
      this.$emit('change', e.target.innerText)
    },
    handleTouchStart () {
      this.touchStatus = true
    },
    handleTouchMove (e) {
      if (this.touchStatus) {
        if (this.timer) {
          clearTimeout(this.timer)
        }
        this.timer = setTimeout(() => {
          const currentY = e.touches[0].clientY - 89
          const index = Math.floor((currentY - this.startY) / 20)
          if (index >= 0 && index <= this.letters.length) {
            this.$emit('change', this.letters[index])
          }
        }, 16)
      }
    },
    handleTouchEnd () {
      this.touchStatus = false
    }
  },
  updated () {
    this.startY = this.$refs.A[0].offsetTop
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'

  .list
    position: absolute
    right: 0
    top: 1.77rem
    bottom: 0
    width: .4rem
    display: flex
    flex-direction: column
    justify-content: center
  .item
    text-align: center
    line-height: .4rem
    color: $bgColor
</style>
