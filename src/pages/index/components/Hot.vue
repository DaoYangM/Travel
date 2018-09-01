<template>
  <div class="hot-group">
    <div class="hot-group-title">
      <div class="title-content">
        <img class="title-content-img" src="http://img1.qunarzz.com/piao/fusion/1711/16/bfbb9874e8f11402.png" alt="">
        <span class="title">本周热门榜单</span>
      </div>
      <div class="title-more">
        <a href="">全部榜单 ></a>
      </div>
    </div>
    <ul class="hot-group-list">
      <li class="list-item" v-for="item in hotList" :key="item.id">
        <a class="item-content" href="">
          <div class="hot-tag-wrap">
            <img class="hot-tag" :src="item.rankImg" alt="">
          </div>
          <div class="hot-img-wrap">
            <img class="hot-img" :src="item.imgUrl" alt="">
          </div>
          <div class="hot-sight">{{ item.sight }}</div>
          <div class="hot-price">
            <span>
              <em class="hot-price-em" v-html="$options.filters.rmb(item.price)"></em>起
            </span>
          </div>
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeHot',
  props: {
    hotList: Array
  },
  data: function () {
    return {
    }
  },
  filters: {
    rmb: function (value) {
      return '&yen;' + value
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/variables.styl';

  ul
    list-style : none
  .hot-group-title
    display : flex
    align-items : center
    justify-content : space-between
    padding : .24rem 0 .26rem

    .title-content
      .title
        display : inline-block
        font-size : .32rem
        color : $ftColor
        height : .44rem
        line-height : .44rem
        margin-left : .08rem

      .title-content-img
        height : .3rem
        width : .3rem
        margin-left : .2rem
        vertical-align :top

    .title-more
      margin-right .32rem

  .hot-group-list
    padding : 0 .24rem
    white-space: nowrap;
    overflow-x : scroll
    display : flex

    .list-item:not(:first-child)
      margin-left : .12rem
    .list-item:last-child
      padding-right : .24rem

    .list-item
      width : 2rem
      position : relative
      padding : .06rem 0 .2rem

      .item-content
        display : flex
        flex-direction : column
        align-items : center
        justify-content : center
        color : $ftColor

        .hot-tag-wrap
          height : .4rem
          width : .84rem
          position : absolute
          top : 0
          align-self : flex-start

          .hot-tag
            width : 100%

        .hot-img-wrap
          width : 2rem

          .hot-img
            width : 100%

        .hot-sight
          margin-top : .12rem
          font-size : .24rem
          line-height : .32rem

        .hot-price
          font-size : .24rem
          line-height : .36rem
          color : #616161

          .hot-price-em
            color : #ff8300
            font-size : .28rem
</style>
