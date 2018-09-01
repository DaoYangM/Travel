<template>
  <div>
    <div class="icons-wrap">
      <swiper :options="swiperOption">
        <!-- slides -->
        <swiper-slide v-for="(page, index) in pages" :key="index">
          <div class="icons">
            <div class="icon" v-for="icon in page" :key="icon.id">
              <img class="icon-wrap-img" :src="icon.imgUrl" alt="">
              <p class="keywords">{{ icon.desc }}</p>
            </div>
          </div>
        </swiper-slide>
        <!-- Optional controls -->
        <div class="swiper-pagination" slot="pagination"></div>
      </swiper>
    </div>

    <div class="map-con">
      <div class="map-con-left">
       <span class="iconfont icon-dingwei" style="font-size: 14px;"> 定位失败</span>
      </div>
      <div class="map-con-right">
        <span class="iconfont icon-diqiu" style="font-size: 14px;"> 玩水季</span>
      </div>
    </div>

    <div class="map-activity-con">
      <div class="map-activity-left">
        <img class="map-activity-left-img" src="http://img1.qunarzz.com/piao/fusion/1806/29/30427c0e0658b502.png" alt="">
      </div>
      <div class="map-activity-right">
        <img class="map-activity-right-img" src="http://img1.qunarzz.com/piao/fusion/1808/84/887ec92cae51f302.png" alt="">
      </div>
    </div>
  </div>

</template>

<script>
export default {
  name: 'HomeIcons',
  props: {
    iconList: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination'
      }
    }
  },
  computed: {
    pages: function () {
      let pags = []
      let i = 0
      for (let index = 0; index < this.iconList.length; index++) {
        if ((index + 1) / 8 === 1) {
          pags[i].push(this.iconList[index])
          i++
        } else {
          if (!pags[i]) {
            pags[i] = []
          }
          pags[i].push(this.iconList[index])
        }
      }
      return pags
    }
  },
  mounted () {
    console.log(this.pages)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/variables.styl';
  .swiper-container >>> .swiper-pagination-bullets
    bottom : 0px
  .swiper-container >>> .swiper-pagination-bullet
    width : .12rem
    height : .12rem
  .icons-wrap
    height : 3.75rem
    .icons
      display: flex;
      flex-wrap : wrap

      .icon
        width : 25%
        height : 1.875rem
        display : flex
        justify-content : center
        align-items : center

        flex-direction : column
        padding-top : 0.1rem

        .icon-wrap-img
          height : 1.1rem
          width : 1.1rem
          margin-bottom : .1rem

          .keywords
            font-size : .28rem
            color : $ftColor

  .map-con
    margin-top : .3rem
    display : flex
    text-align : center
    height : .98rem
    line-height : .98rem
    color : $ftColor
    font-size : .28rem
    box-sizing : border-box

    .map-con-left
      flex-grow : 1
      flex-shrink : 0
      border-top : 1px solid #eee
      border-right : 1px solid #eee
      width : 50%

    .map-con-right
      flex-grow : 1
      flex-shrink : 0
      border-top : 1px solid #eee
      width : 50%

  .map-activity-con

    height : 1.8rem
    display : flex
    border-bottom : .2rem solid #eee
    border-top : .2rem solid #eee
    box-sizing : border-box

    .map-activity-left
      flex-shrink : 0
      flex-grow : 1
      width : 50%
      border-right : .02rem solid #eee
      text-align : center

      .map-activity-left-img
        height : 100%

    .map-activity-right
      flex-shrink : 0
      flex-grow: 1
      width : 50%
      text-align : center

      .map-activity-right-img
        height : 100%
</style>
