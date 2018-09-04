<template>
  <div>
    <city-header></city-header>
    <city-container :cityData="cityData"></city-container>
  </div>
</template>

<script>
import CityHeader from './components/Header'
import CityContainer from './components/Container'

import axios from 'axios'

export default {
  name: 'City',
  data () {
    return {
      cityData: Object
    }
  },
  components: {
    CityHeader,
    CityContainer
  },
  methods: {
    handleCityJson (value) {
      this.cityData = value['data']['data']
    }
  },
  mounted () {
    axios.get('/api/city.json')
      .then(this.handleCityJson)
  }
}
</script>

<style lang="stylus" scoped>

</style>
