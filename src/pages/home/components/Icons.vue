<template>
    <div class="icons">
      <swiper :options="swiperOptionIcon">
          <swiper-slide v-for="(page, index) of pages" :key="index">
            <div class="icon" v-for="item of page" :key="item.id">
                <div class="icon-image"><img class="icon-image-content" :src="item.imgUrl" /></div>
                <p class="icon-desc">{{item.desc}}</p>
            </div>
          </swiper-slide>
      </swiper>
    </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      swiperOptionIcon: {
        autoplay: false
      },
      iconList: [{
        id: '0001',
        imgUrl: 'https://www.toni.tw/icon6.png',
        desc: '景點門票'
      }, {
        id: '0002',
        imgUrl: 'https://www.toni.tw/icon6.png',
        desc: '泡溫泉'
      }, {
        id: '0003',
        imgUrl: 'https://www.toni.tw/icon6.png',
        desc: '植物園'
      }, {
        id: '0004',
        imgUrl: 'https://www.toni.tw/icon6.png',
        desc: '一日遊'
      }, {
        id: '0005',
        imgUrl: 'https://www.toni.tw/icon6.png',
        desc: '必逛'
      }, {
        id: '0006',
        imgUrl: 'https://www.toni.tw/icon6.png',
        desc: '山水相逢'
      }, {
        id: '0007',
        imgUrl: 'https://www.toni.tw/icon6.png',
        desc: '自然風光'
      }, {
        id: '0008',
        imgUrl: 'https://www.toni.tw/icon6.png',
        desc: '名勝古蹟'
      }, {
        id: '0009',
        imgUrl: 'https://www.toni.tw/icon6.png',
        desc: '歷史遺物'
      }, {
        id: '0010',
        imgUrl: 'https://www.toni.tw/icon6.png',
        desc: '荒郊野外'
      }]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
    @import '~styles/iconfont/variables.styl'
    @import '~styles/iconfont/mixin.styl'
    .icons >>> .swiper-container
        height: 0
        padding-bottom: 50%
    .icons
      margin-top: .1rem
      .icon
          position: relative
          overflow: hidden
          float: left
          width: 25%
          height: 0
          padding-bottom: 25%
          .icon-image
              position: absolute
              top: 0
              left: 0
              right: 0
              bottom: .4rem
              box-sizing: border-box
              padding: .1rem
              .icon-image-content
                  display: block
                  margin: 0 auto
                  height: 100%
          .icon-desc
              position: absolute
              left: 0
              right: 0
              bottom: 0
              height: .44rem
              text-align: center
              color: $darkTextColor
              ellipsis()
</style>
