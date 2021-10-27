<template>
  <div>
      <div>
      <div
      class="item"
      v-for="(item, index) of list"
      :key="index"
      >
        <div class="item-title border-bottom" @click.stop="handleTitleClick">
          <span class="iconfont">&#xe624;</span>
          {{item.title}}
        </div>
        <div v-if="item.children" class="item-children" v-show="toggleChild" key="index">
          <detail-list :list="item.children"></detail-list>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailList',
  props: {
    list: Array
  },
  data () {
    return {
      toggleChild: true
    }
  },
  methods: {
    handleTitleClick () {
      this.toggleChild = !this.toggleChild
    }
  }
}
</script>

<style lang="stylus" scoped>
  .title
    margin-top: .2rem
    line-height: .8rem
    background: #eee
    text-indent: .2rem
    ellipsis()
  .item-title
    line-height: .8rem
    font-size: .32rem
    padding: 0 .2rem
    .iconfont
      font-size: .20rem
      color: #666
  .item-children
    padding: 0 .2rem
</style>
