<template>
  <div class="head-back" v-if="backShow">
    <router-link tag="div" to="/" class="header-back-icon"><div class="iconfont back-icon">&#xe624;</div></router-link>
  </div>
  <div class="header-bar" :style="opacityStyle" v-else>
    <router-link tag="div" to="/" class="header-back-icon"><div class="iconfont back-icon">&#xe624;</div></router-link>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      backShow: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      let top = document.documentElement.scrollTop
      if (top > 10) {
        this.opacityStyle.opacity = top / 120
        this.backShow = false
      } else {
        this.backShow = true
      }
    }
  },
  activated () {
    document.documentElement.scrollTop = 0
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/variables.styl';
  .head-back
    position : absolute
    left : .1rem
    top : .1rem
    width : .72rem
    height : .72rem
    color : #ffffff
    z-index : 2

    .header-back-icon
      width : .72rem
      height : .72rem
      line-height : .72rem
      text-align : center
      font-weight : bold

  .header-bar
    position : fixed
    top : 0
    left : 0
    width : 100%
    background : $bgColor
    opacity : 1
    z-index : 2
    color : #ffffff

    .header-back-icon
      margin-top : .1rem
      margin-left : .1rem
      width : .72rem
      height : .72rem
      line-height : .72rem
      text-align : center
      font-weight : bold
</style>
