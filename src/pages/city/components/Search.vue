/* eslint-disable indent */
<template>
  <div>
    <div class="search">
      <input
      class="search-input"
      type="text"
      v-model="keyword"
      placeholder="请输入城市名或拼音"
      onfocus="this.placeholder=''"
      onblur="this.placeholder='请输入城市名或拼音'">
    </div>
  <div class="search-content"
  ref="search"
  v-show="keyword">
    <ul>
      <li class="search-item border-bottom"
      v-for="item of list"
      :key="item.id"
      @click="handleCityClick(item.name)"
      >{{item.name}}</li>
      <li class="search-item border-bottom"
      v-show="hasNoData">
      无匹配项</li>
    </ul>
  </div>
  </div>
</template>
<script>
import Bscroll from 'better-scroll'
import { mapMutations } from 'vuex'
export default {
  name: 'CitySearch',
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
  mounted () {
    this.scroll = new Bscroll(this.$refs.search)
  },
  updated () {
    this.scroll.refresh()
  },
  watch: {
    keyword () {
      if (this.timer) clearTimeout(this.timer)
      if (!this.keyword) {
        this.list = []
        return
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
@import '~styles/iconfont/varibles.styl'
  .search
    height: .72rem
    padding: 0 .1rem
    background-color: $bgColor
    .search-input
      width: 100%
      box-sizing: border-box
      height: .62rem
      line-height: .62rem
      text-align: center
      border-radius: .06rem
      color: #666
      padding: 0 .1rem
  .search-content
    z-index: 1
    overflow: hidden
    top: 1.58rem
    left: 0
    right: 0
    bottom: 0
    background-color: #eee
    position: absolute
    .search-item
      line-height: .50rem
      padding-left: .2rem
      background-color: #fff
      color: #666
</style>
