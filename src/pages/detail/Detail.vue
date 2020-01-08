<template>
  <div>
    <detail-banner></detail-banner>
    <detail-header></detail-header>
    <div class="content">
      <detail-list></detail-list>
    </div>
  </div>
</template>

<script>
import DetailBanner from './components/Banner'
export default {
  name: 'Detail',
  components: {
    DetailBanner
  },
  data () {
    return {
    }
  }
}
</script>

<style lang="stylus" scoped>
</style>
