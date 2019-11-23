<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list :currentCity="currentCity" :hotCities="hotCities" :cities="cities"></city-list>
    <city-alphabet :cities="cities"></city-alphabet>
  </div>
</template>

<script>
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
import axios from 'axios'

export default{
  name: 'City',
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  data () {
    return {
      currentCity: '',
      hotCities: [],
      cities: {}
    }
  },
  methods: {
    getInfo () {
      axios.get('/api/city.json')
        .then(this.getInfoSucc)
    },
    getInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        var data = res.data
        this.currentCity = data.currentCity
        this.hotCities = data.hotCities
        this.cities = data.cities
      }
    }
  },
  mounted () {
    this.getInfo()
  }
}
</script>

<style>
</style>
