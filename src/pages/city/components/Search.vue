<template>
  <div>
    <div class="search">
      <input type="text" class="search-input" placeholder="输入城市名或拼音"
        v-model="content"
      >
    </div>
    <div ref="searchlist" class="search-list" v-show="content">
      <ul>
        <li class="search-item border-bottom" v-for="item in list" :key="item.id" @click="handleClick(item.name)">{{item.name}}</li>
        <li class="search-item" v-show="hasNoContent">没有找到匹配数据</li>
      </ul>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
import { mapMutations } from 'vuex'

export default{
  name: 'CitySearch',
  data () {
    return {
      content: '',
      list: [],
      timer: null
    }
  },
  props: {
    cities: Object
  },
  watch: {
    content () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach((value) => {
            if (value.spell.indexOf(this.content) > -1 || value.name.indexOf(this.content) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  computed: {
    hasNoContent () {
      return !this.list.length
    }
  },
  methods: {
    handleClick (city) {
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.searchlist)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'

  .search
    background-color: $bgColor
    height: .72rem
    padding: .1rem
    margin-top: -0.01rem
    .search-input
      box-sizing: border-box
      border-radius: .06rem
      height: .68rem
      line-height: .68rem
      width: 100%
      text-align: center
      color: #666
      padding 0 .1rem
  .search-list
    background-color: #eee
    position: absolute
    top: 1.77rem
    bottom: 0
    left: 0
    right: 0
    z-index: 1
    overflow: hidden
    .search-item
      padding-left: .2rem
      line-height: .62rem
      color: #666
      background-color: #fff
</style>
