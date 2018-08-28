<template>
    <div>
        <home-header></home-header>
        <HomeSwiper></HomeSwiper>
        <home-icons></home-icons>
    </div>
</template>

<script>

import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'

export default {
  name: 'Index',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons
  }
}
</script>

<style>
</style>
