<template>
  <div class="header">
    城市选择
    <router-link to="/">
      <div class="iconfont back-header">&#xe624;</div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    position relative
    overflow hidden
    height $HeaderHeight
    line-height $HeaderHeight
    font-size .32rem
    color #ffffff
    text-align center
    background-color $bgColor
    .back-header
      position absolute
      width .64rem
      left 0
      top 0
      font-size: .4rem
      color #ffffff
</style>
