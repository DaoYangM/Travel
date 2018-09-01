<template>
    <div>
        <home-header :city="city"></home-header>
        <home-swiper :swiperList="swiperList"></home-swiper>
        <home-icons :iconList="iconList"></home-icons>
        <home-hot :hotList="hotList"></home-hot>
        <home-like :likeList="likeList"></home-like>
    </div>
</template>

<script>

import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeHot from './components/Hot'
import HomeLike from './components/Like'

import axios from 'axios'

export default {
  name: 'Index',
  data () {
    return {
      city: '',
      swiperList: [],
      iconList: [],
      hotList: [],
      likeList: []
    }
  },
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeHot,
    HomeLike
  },
  mounted () {
    axios.get('/api/index.json')
      .then(this.printContent)
  },
  methods: {
    printContent: function (value) {
      this.city = value.data.data.city
      this.swiperList = value.data.data.swiperList
      this.iconList = value.data.data.iconList
      this.hotList = value.data.data.hotList
      this.likeList = value.data.data.likeList
    }
  }
}
</script>

<style>
</style>
