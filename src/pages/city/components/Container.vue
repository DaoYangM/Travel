<template>
  <div class="wrapper" ref="wrapper">
    <div class="content">
      <div class="city-item">
        <h2 class="city-type">热门城市</h2>
        <div class="citys">
          <div class="city" v-for="i of cityData.hotCities" :key="i.id">{{ i.name }}</div>
        </div>
      </div>
      <div class="city-item">
        <h2 class="city-type">字母排序</h2>
        <div class="citys">
          <div class="city-p" @click="handlePTouch(i)" v-for="i of character" :key="i">{{ i }}</div>
        </div>
      </div>
      <div class="city-item" v-for="(city, p) of cityData.cities" :key="p">
        <h2 class="city-type" :ref="p">{{ p }}</h2>
        <div class="citys">
          <div class="city city-a" v-for="i of city" :key="i.id" @click="handleCityHange(i.name)">{{ i.name }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'

export default {
  name: 'CityContainer',
  props: ['cityData'],
  data () {
    return {
      character: ['A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'J', 'k', 'L', 'M', 'N', 'P', 'Q', 'S', 'T', 'W', 'X', 'Y', 'Z']
    }
  },
  mounted () {
    this.$nextTick(() => {
      this.scroll = new BScroll(this.$refs.wrapper, {})
    })
  },
  methods: {
    handlePTouch (p) {
      this.scroll.scrollToElement(this.$refs[p][0])
      console.log(p)
      console.log(this.$refs[p][0])
    },
    handleCityHange (city) {
      this.$store.dispatch('changeCity', city)
      this.$router.push('/')
      console.log(city)
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/variables.styl'

  .wrapper
    overflow:  hidden
    position : absolute
    top : 1.50rem
    left : 0
    right : 0
    bottom : 0
    z-index : 1

    .city-type
      font-size : .24rem
      border : .24rem solid #f5f5f5
      background : #f5f5f5

    .citys
      display : flex
      flex-wrap : wrap
      line-height : .9rem

      .city
        width : 33%
        text-align : center
        height : .9rem
        box-sizing : border-box
        border-bottom : .02rem solid #ddd
        border-left : .02rem solid #ddd
        border-right : .02rem solid #ddd

      .city-p
        width : 16.66%
        height : .9rem
        text-align : center

       .city-a
        width : 25%
</style>
