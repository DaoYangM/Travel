<template>
<div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="image of swiperList" :key="image.id">
        <img class="swiper-img" :src="image.imgUrl" alt="" srcset="">
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
</div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    swiperList: Array
  },
  data: function () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        autoplay: 3000,
        loop: true
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #ffffff
  .wrapper >>> .swiper-pagination-bullet
    width : 0.12rem
    height : 0.12rem
  .wrapper
    .swiper-img
      width : 100%
</style>
