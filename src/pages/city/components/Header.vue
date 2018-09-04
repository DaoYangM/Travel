<template>
  <div class="header">
    <div class="header-title-container">
      <div class="header-back">
        <router-link to="/"><span class="iconfont icon-fanhui"></span></router-link>
      </div>
      <div class="header-title">
        城市选择
      </div>
    </div>
    <div class="region-tab-container">
      <div class="region-tab">
        <div class="domestic">境内</div>
        <div class="foreign">境外</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/variables.styl'

    .header
        background : #f5f5f5

      .header-title-container
        line-height : .68rem
        color : #ffffff
        display : flex
        position : relative
        background : $bgColor
        .header-back
          color : #ffffff
          height : .68rem
          width : .80rem
          left : 0
          // top: 50%
          position : absolute

          .icon-fanhui
            color : #ffffff
            display : block
            width : 100%
            text-align : center

        .header-title
          flex : 1
          margin : 0 1rem
          text-align : center
          font-size : .32rem
          white-space: nowrap
          text-overflow: ellipsis
          line-height : .68rem

      .region-tab-container
        padding : 0 1rem
        background : $bgColor
        height : .80rem
        display : flex
        align-items : center

        .region-tab
          display : flex
          text-align : center
          font-size : .28rem
          height : .4rem
          flex: 1
          border-radius: .03rem;
          border: 1px solid #fff;

          .domestic
            flex : 1
            background :  #ffffff
            line-height : .40rem
            color : $bgColor

           .foreign
              flex : 1
              line-height : .40rem
              color : #ffffff

</style>
