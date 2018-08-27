<template>
    <div class="header">
      <div class="header-left"><div class="iconfont back-icon">&#xe624;</div></div>
      <div class="header-input"><span class="iconfont icon-sousuo"></span> 输入城市/景点/游玩主题</div>
      <div class="header-right"><span class="iconfont icon-arrow-down"></span> 城市</div>
    </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/variables.styl';
  .header
    display : flex
    justify-content : center
    line-height : .86rem
    background : $bgColor

    .header-left
      width : .64rem
      color : #ffffff;

      .back-icon
        text-align : center;

    .header-input
      flex: 1
      height : 0.64rem
      margin-top : .12rem
      margin-left : .2rem
      line-height : 0.64rem
      background : #ffffff
      border-radius : 0.1rem
      color : #ccc;
      padding-left : .2rem

    .header-right
      width : 1.24rem
      text-align : center
      color : #ffffff;
</style>
