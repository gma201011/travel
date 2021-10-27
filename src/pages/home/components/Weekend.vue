<template>
<div>
  <div class="title">假日好去處</div>
  <ul>
    <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl">
        </div>
      <div class="item-info">
        <p class="item-title">{{item.title}}</p>
        <p class="item-desc">{{item.desc}}</p>
      </div>
    </li>
  </ul>
</div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data () {
    return {
      recommendList: [{
        id: '0001',
        imgUrl: 'https://www.travel.taipei/image/64552/1024x768',
        title: '地熱谷 地獄谷 鬼湖',
        desc: '終年煙霧繚繞的台灣八勝十二景之一'
      }, {
        id: '0002',
        imgUrl: 'https://www.travel.taipei/image/175030/1024x768',
        title: '北投公園露天溫泉浴池 千禧湯',
        desc: '泉水為氯離子硫酸鹽泉，又稱青磺泉'
      }, {
        id: '0003',
        imgUrl: 'https://www.travel.taipei/image/1748/1024x768',
        title: '貓空纜車',
        desc: '「貓纜之眼」水晶車廂可以360度飽覽貓空美景'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/iconfont/mixin.styl'
  .title
    line-height: .8rem
    background: #eee
    text-indent: .2rem
    ellipsis()
  .item-img-wrapper
    overflow: hidden
    height: 0
    padding-bottom: 33.9%
  .item-img
    width: 100%
  .item-info
    padding: .1rem
    .item-title
      line-height: .54rem
      font-size: .32rem
      ellipsis()
    .item-desc
      line-height: .4rem
      color: #ccc
      ellipsis()
</style>
