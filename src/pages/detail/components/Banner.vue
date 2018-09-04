<template>
  <div>
    <div class="head-figure" v-if="!showSwiper" @click="showSwiper = !showSwiper">
      <div class="head-figure-wrap">
        <img class="head-figure-img" src="//img1.qunarzz.com/sight/p0/1711/3d/3dd240b987290356a3.img.jpg_600x330_3ae5036d.jpg" alt="">
      </div>
      <div class="head-figure-info">
        <div class="head-figure-title">桂林锦龙国际赛车场</div>
      </div>
      <div class="head-imgswiper">
        <span class="iconfont icon-xiangce"></span>
        <em class="head-imgswiper-number">4</em>
      </div>
    </div>
    <div class="header-hiden-swiper" @click="showSwiper = !showSwiper" v-else>
      <div class="swiper-img-wrap">
        <swiper :options="swiperOption">
            <swiper-slide>
              <img class="swiper-img" src="http://img1.qunarzz.com/sight/p0/1711/3d/3dd240b987290356a3.img.jpg_r_800x800_1dd8ba99.jpg" alt="">
            </swiper-slide>
            <swiper-slide>
              <img class="swiper-img" src="http://img1.qunarzz.com/sight/p0/1711/3d/3dd240b987290356a3.img.jpg_r_800x800_1dd8ba99.jpg" alt="">
            </swiper-slide>
        </swiper>
        <div class="swiper-pagination" slot="pagination"></div>
      </div>
    </div>
  </div>

</template>

<script>
export default {
  name: 'DetailBanner',
  data () {
    return {
      showSwiper: false,
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction'
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
  .header-hiden-swiper >>> .swiper-pagination-fraction
    bottom: 1rem
    color : #ffffff
  .head-figure
    position : relative

    .head-figure-wrap
      width : 100%
      height : 0
      padding-bottom : 55%

      .head-figure-img
        width : 100%

    .head-figure-info
      overflow : hidden
      position : absolute
      bottom : .36rem
      right : .2rem
      left : .2rem
      min-height : .4rem

      .head-figure-title
        line-height : .4rem
        color : #ffffff
        font-size : .36rem
        z-index : 1
        text-shadow: 0 1px 2px rgba(0,0,0,0.70)

    .head-imgswiper
      width : 1.2rem
      height : .4rem
      line-height : .4rem
      background : rgba(0, 0, 0, .5)
      border-radius : .2rem
      text-align : center
      color : #ffffff
      font-size : .24rem
      position : absolute
      left : .2rem
      bottom : .86rem

      .icon-xiangce
        font-size : .24rem

      .head-imgswiper-number
        margin-left : .04rem
        line-height : .4rem

  .header-hiden-swiper
    position : fixed
    overflow : hidden
    z-index : 99
    bottom : 0
    top : 0
    background : #000000
    width: 100%;
    height : 100%
    display : flex
    flex-direction : column
    justify-content : center
    align-items : center

    .swiper-img-wrap
      width : 100%
      overflow : hidden
      height : 0
      padding-bottom : 80%
      .swiper-img
        width: 100%;
        background-position: center;
        background-repeat: no-repeat;
        background-size: contain;
</style>
