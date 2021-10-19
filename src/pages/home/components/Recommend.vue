<template>
<div>
  <div class="recommend-title">熱門推薦</div>
  <ul>
    <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <img class="item-img" :src="item.imgUrl">
      <div class="item-info">
        <p class="item-title">{{item.title}}</p>
        <p class="item-desc">{{item.desc}}</p>
        <button class="item-button">查看詳情</button>
      </div>
    </li>
  </ul>
</div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [{
        id: '0001',
        imgUrl: 'https://www.travel.taipei/image/213782/1024x768',
        title: '士林官邸 士林官邸公園',
        desc: '過去為故總統蔣中正與蔣夫人宋美齡的住所'
      }, {
        id: '0002',
        imgUrl: 'https://www.travel.taipei/image/64355/1024x768',
        title: '南港山系 象山親山步道',
        desc: '市郊踏青的好去處'
      }, {
        id: '0003',
        imgUrl: 'https://www.travel.taipei/image/88027/1024x768',
        title: '寧夏觀光夜市',
        desc: '人車分路的夜市，好逛又安全'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/iconfont/mixin.styl'
  .recommend-title
    margin-top: .2rem
    line-height: .8rem
    background: #eee
    text-indent: .2rem
    ellipsis()
  .item
    overflow: hidden
    display: flex
    height: 1.9rem
    .item-img
      width: 1.7rem
      height: 1.7rem
      padding: .1rem
    .item-info
      flex: 1
      padding: .1rem
      min-width: 0
      .item-title
        line-height: .54rem
        font-size: .32rem
        ellipsis()
      .item-desc
        line-height: .4rem
        color: #ccc
        ellipsis()
      .item-button
        line-height: .44rem
        margin-top: .16rem
        background: #ff9300
        padding: 0 .2rem
        border-radius: .06rem
        color: #fff
</style>
