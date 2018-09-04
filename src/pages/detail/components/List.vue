<template>
  <div class="ticket-container">
    <div class="ticket-group" :style="marginLeftStyle" v-for="(item, index) in list" :key="index">
      <h3 class="ticket-title"><span class="ticket-title-img"></span> {{ item.title }}</h3>
      <template v-if="item.child">
        <detail-list :list="item.child" :time="time+1"></detail-list>
      </template>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailList',
  props: {
    list: Array,
    time: Number
  },
  data () {
    return {
      marginLeftStyle: {
        'margin-left': this.time * 0.4 + 'rem'
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
  .ticket-group
    .ticket-title
      font-size : .32rem
      line-height : .88rem
      height : .88rem

      .ticket-title-img
        display: inline-block
        width: .36rem
        height: .36rem
        line-height : .88rem
        vertical-align : middle
        background: url(//s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat
        margin-right: .1rem
        background-size: .4rem 3rem
</style>
