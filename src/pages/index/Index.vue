<template>
    <div>
        <home-header></home-header>
        <HomeSwiper></HomeSwiper>
        <div>test</div>
    </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
export default {
  name: 'Index',
  components: {
    HomeHeader,
    HomeSwiper
  }
}
</script>

<style>
</style>
