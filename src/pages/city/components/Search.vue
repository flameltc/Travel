<template>
  <div>
    <div class="search">
      <input v-model="keyword" type="text" class="input-search" placeholder="输入城市名或拼音">
    </div>
    <div class="search-content" v-show="keyword" ref="search">
      <ul>
        <li v-for="item of list" :key="item.id" class="search-item border-bottom" @click="handleCityClick(item.name)">{{item.name}}</li>
        <li class="search-item border-bottom" v-show="hasNoData">没有找到地点</li>
      </ul>
    </div>
  </div>
</template>

<script>
import Bscoll from 'better-scroll'
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
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach((value) => {
            if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  methods: {
    handleCityClick (city) {
      this.$store.commit('changeCity', city)
      this.$router.push('/')
      this.keyword = ''
    }
  },
  mounted () {
    this.scoll = new Bscoll(this.$refs.search)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .search
    background-color $bgColor
    padding 0 .1rem
    height .72rem
    .input-search
      box-sizing border-box
      width 100%
      height .62rem
      line-height .62rem
      text-align center
      border-radius .06rem
      color #666
      padding 0 .1rem
  .search-content
    z-index 1
    overflow hidden
    position absolute
    top 1.58rem
    left 0
    right 0
    bottom 0
    background #eeeeee
    .search-item
      line-height .62rem
      padding-left  .2rem
      color #666
      background-color #fff
</style>
