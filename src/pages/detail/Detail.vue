<template>
    <div>
      <detail-banner></detail-banner>
      <detail-header></detail-header>
      <detail-list :list="normalList"></detail-list>
      <detail-list :list="specialList"></detail-list>
      <detail-map></detail-map>
      <div class="content"></div>
    </div>
</template>

<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
import DetailMap from './components/Map'
export default ({
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailList,
    DetailMap
  },
  data () {
    return {
      normalList: [{
        title: '成人票',
        children: [{
          title: '成人團票',
          children: [{
            title: '成人三人行團票 200'
          }, {
            title: '成人五人行團票 300'
          }]
        }]
      }],
      specialList: [{
        title: '特殊票',
        children: [{
          title: '幼童票 30'
        }, {
          title: '敬老票 40'
        }, {
          title: '軍警票 35'
        }, {
          title: '身障票 20'
        }
        ]
      }]
    }
  }
})
</script>

<style lang="stylus" scoped>
  .detail-map
    margin-top: 1rem
</style>
