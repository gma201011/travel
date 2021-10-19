<template>
    <div class="wrapper">
        <swiper :options="swiperOption">
            <!-- slides -->
            <swiper-slide v-for="item of swiperList" :key="item.id">
            <!--eslint-disable-next-line-->
  	            <img class="swiper-img" :src="item.imgUrl" />
            </swiper-slide>
            <!-- Optional controls -->
            <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
    </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
        id: '0001',
        imgUrl: 'https://www.travel.taipei/image/219467/compressed'
      }, {
        id: '0002',
        imgUrl: 'https://www.travel.taipei/image/219157/compressed'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
    .wrapper >>> .swiper-pagination-bullet-active
        background: #fff

    .swiper-img
        height: 25vh
        background: #eee
        width:100%
        @media screen and (min-width:600px){
          height: 80vh
        }
</style>
