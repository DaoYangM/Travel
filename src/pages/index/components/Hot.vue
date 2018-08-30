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
  data: function () {
    return {
      hotList: [
        {id: '001', imgUrl: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_150x150_06cb3e52.jpg', sight: '故宫', price: '20', rankImg: 'http://img1.qunarzz.com/piao/fusion/1710/ab/159673b63e6ca702.png'},
        {id: '002', imgUrl: 'http://img1.qunarzz.com/sight/p0/1708/2b/2b3b94de99c0a425a3.img.jpg_150x150_2dec3e78.jpg', sight: '八达岭长城', price: '40', rankImg: 'http://img1.qunarzz.com/piao/fusion/1710/2d/36d0c4adaebbbc02.png'},
        {id: '003', imgUrl: 'http://img1.qunarzz.com/sight/p0/201306/13/bdf22f69fab0ee4ec8d65eac.jpg_150x150_35b4b15f.jpg', sight: '八达岭长城缆车', price: '160', rankImg: 'http://img1.qunarzz.com/piao/fusion/1710/67/edc47ffef9e96b02.png'},
        {id: '004', imgUrl: 'http://img1.qunarzz.com/sight/p0/1505/d2/d274c92de14c93da.water.jpg_150x150_2747e538.jpg', sight: '颐和园', price: '40', rankImg: ''},
        {id: '005', imgUrl: 'http://img1.qunarzz.com/sight/p0/1501/40/40b2b6c951b28fdd.water.jpg_150x150_8a63d940.jpg', sight: '水立方', price: '14', rankImg: ''},
        {id: '006', imgUrl: 'http://img1.qunarzz.com/sight/p0/1505/f5/f5f45e1a83537bcb.water.jpg_150x150_2a3c9117.jpg', sight: '圆明园', price: '9.8', rankImg: ''},
        {id: '007', imgUrl: 'http://img1.qunarzz.com/sight/p0/1508/a5/4003f9dd7bebf61eccbf64046e26d487.water.jpg_150x150_27594131.jpg', sight: '北京欢乐谷', price: '29.9', rankImg: ''},
        {id: '008', imgUrl: 'http://img1.qunarzz.com/sight/p0/1507/36/ce3d2d6c9ab44d67ae68d940b8781829.water.jpg_150x150_e7957917.jpg', sight: '北京野生动物园', price: '71', rankImg: ''}

      ]
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
