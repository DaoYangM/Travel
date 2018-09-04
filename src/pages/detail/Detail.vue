<template>
  <div>
    <detail-header></detail-header>
    <detail-banner></detail-banner>
    <detail-list :list="list" :time="0"></detail-list>
  </div>
</template>

<script>
import DetailHeader from './components/Header'
import DetailBanner from './components/Banner'
import DetailList from './components/List'

export default {
  name: 'Detail',
  data () {
    return {
      list: [
        {title: '成人票', child: [{title: '成人票1', child: [{title: '成人票2'}]}]},
        {title: '儿童票'},
        {title: '老人票'}
      ]
    }
  },
  mounted () {
    console.log(this.$route.params.id)
  },
  components: {
    DetailHeader,
    DetailBanner,
    DetailList
  }
}
</script>

<style lang="stylus" scoped>

</style>
