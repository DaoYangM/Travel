<template>
<div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="image of imageList" :key="image.id">
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
  data: function () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        autoplay: 3000,
        loop: true
      },

      imageList: [
        {id: '001', imgUrl: 'http://img1.qunarzz.com/piao/fusion/1808/b0/a123fba6d7e3dd02.jpg_750x200_1425741a.jpg'},
        {id: '002', imgUrl: 'http://img1.qunarzz.com/piao/fusion/1801/bd/04554e7c67650302.jpg_750x200_4293d60a.jpg'},
        {id: '003', imgUrl: 'http://img1.qunarzz.com/piao/fusion/1807/66/e5a5cec881702f02.jpg_750x200_67bb5691.jpg'},
        {id: '004', imgUrl: 'http://img1.qunarzz.com/piao/fusion/1808/f4/5f2289f8675f0502.jpg_750x200_ab1633c7.jpg'}

      ]
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
