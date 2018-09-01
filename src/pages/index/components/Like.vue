<template>
  <div class="like-group">
    <div class="like-title-con">
      <img class="like-title-img" src="http://img1.qunarzz.com/piao/fusion/1711/89/ebc329f16c55bb02.png" alt="">
      <span class="like-title">猜你喜欢</span>
    </div>
    <ul class="like-group-list">
      <li class="like-group-item" v-for="item of likeList" :key="item.id">
        <a class="like-fulllink" href="">
          <div class="like-fulllink-tag" style="background-image:url(https://img1.qunarzz.com/piao/fusion/1802/52/b9080e45b69b4f02.png)">
            可订明日
          </div>
          <div class="like-fulllink-img-con">
            <img class="like-fulllink-img" :src="item.imgUrl" alt="">
          </div>
          <div class="like-fulllink-info">
            <div class="like-fulllink-info-title">
              {{ item.title }}
            </div>
            <div class="like-fulllink-info-comment">
              <div class="info-comment-star">
                <div class="star-rating-top" v-bind:style="{width: starRating(item.rating)}">
                  <span></span>
                  <span></span>
                  <span></span>
                  <span></span>
                  <span></span>
                </div>
                <div class="star-rating-bottom">
                  <span></span>
                  <span></span>
                  <span></span>
                  <span></span>
                  <span></span>
                </div>
              </div>
              <span class="info-comment-count">{{ item.comment }}条评论</span>
            </div>
            <div class="like-fulllink-info-price">
              <span class="info-price">
                <span class="yuan">&yen;</span>
                <em class="price">{{ item.price }}</em> 起</span>
              <span class="info-location">{{ item.location }}</span>
            </div>
          </div>
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeLike',
  props: {
    likeList: Array
  },
  filters: {
    rmb: function (value) {
      return '&yen;' + value
    }
  },
  methods: {
    starRating: function (value) {
      return (value / 5) * 100 + '%'
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/variables.styl';
  .like-group
    border-top : .2rem solid #e0e0e0

    .like-title-con
      padding : .24rem 0 .26rem

      .like-title-img
        margin-left : .2rem
        width : .3rem
        height : .3rem

      .like-title
        height : .44rem
        line-height : .44rem
        color : $ftColor

    .like-group-list
      list-style : none
      margin-left : .2rem

      .like-group-item
        padding : .2rem 0
        border-bottom : .02rem solid #eee

        .like-fulllink
          display : flex
          width : 100%
          height : 100%
          position : relative

          .like-fulllink-tag
            width : 1.02rem
            height : .38rem
            position : absolute
            padding-left : .02rem
            color : #ffffff
            font-size : .2rem
            line-height : .38rem
            background-size: 100%;

          .like-fulllink-img-con
            width : 2rem
            height : 2rem

            .like-fulllink-img
              width : 100%

          .like-fulllink-info
            flex : 1
            margin-left : .22rem
            display : flex
            flex-direction : column

            .like-fulllink-info-title
              height : .44rem
              line-height : .44rem
              font-size : .32rem
              color : $ftColor
              margin-top : .26rem

            .like-fulllink-info-comment
              display : flex
              margin-top : .14rem

              .info-comment-star
                margin-right : .44rem
                unicode-bidi: bidi-override;
                color: #ddd;
                font-size: 0;
                height: 25px;
                position: relative;
                padding: 0;
                text-shadow: 0px 1px 0 #a2a2a2;
                display : table

                span
                  padding: 2px;
                  font-size: 15px;

                span:after
                  content: "★"

                .star-rating-top
                  color: #FFD700;
                  padding: 0;
                  position: absolute;
                  z-index: 1;
                  display: block;
                  top: 0;
                  left: 0;
                  overflow: hidden;
                  white-space: nowrap;

                .star-rating-bottom
                    padding: 0;
                    display: block;
                    z-index: 0;

              .info-comment-count
                color : $ftColor
                font-size : .24rem
                line-height : .34rem

            .like-fulllink-info-price
              display : flex
              justify-content : space-between
              margin-top : .22rem
              width : 100%
              font-size : .24rem
              color : $ftColor
              line-height : .4rem

              .info-price
                display : block

                .yuan
                  font-size : .24rem
                  color : #ff8300

                .price
                  font-size : .4rem
                  color : #ff8300

              .info-location
                display : block
                margin-right : .24rem
</style>
