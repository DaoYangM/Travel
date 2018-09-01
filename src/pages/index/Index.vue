<template>
    <div>
        <home-header></home-header>
        <HomeSwiper></HomeSwiper>
        <home-icons></home-icons>
        <home-hot></home-hot>
        <home-like></home-like>
    </div>
</template>

<script>

import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeHot from './components/Hot'
import HomeLike from './components/Like'

export default {
  name: 'Index',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeHot,
    HomeLike
  }
}
</script>

<style>
</style>
