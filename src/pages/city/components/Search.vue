<template>
  <div>
    <div class="search">
      <input v-model="keyword" class="search-input" type="text" placeholder="輸入城市名與中英文關鍵字" />
    </div>
    <div
      class="search-content"
      ref="search"
      v-show="keyword"
      >
      <ul>
        <li
          class="serach-item border-bottom"
          v-for="item of list"
          :key="item.id"
          @click="handleCityClick(item.name)"
        >
          {{item.name}}
        </li>
        <li class="serach-item border-bottom" v-show="hasNoData">
          沒有找到相關數據！
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import { mapMutations } from 'vuex'
export default {
  name: 'CityHeader',
  props: {
    cities: Object
  },
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  methods: {
    handleCityClick (city) {
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  },
  computed: {
    hasNoData () {
      return !this.list.length
    }
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        return (this.list = [])
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach((value) => {
            if (value.spell.indexOf(this.keyword) > -1 ||
                value.name.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/iconfont/variables.styl'
    .search
      height: .72rem
      padding: 0 .1rem
      background: $bgColor
      .search-input
          box-sizing: border-box
          width: 100%
          height: .62rem
          padding: 0 .1rem
          line-height: .62rem
          border-radius: .06rem
          text-align: center
          color: #666
    .search-content
      z-index: 1
      overflow: hidden
      position: absolute
      top: 1.58rem
      left: 0
      right: 0
      bottom: 0
      background: #eee
      .serach-item
          line-height: .62rem
          padding-left: .2rem
          background: #fff
          color: #666
</style>
