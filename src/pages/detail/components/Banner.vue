<template>
  <div>
    <div class="banner" @click="handleGalleryClick">
      <img class="banner-img" src="//img1.qunarzz.com/sight/p0/201401/06/3fbbddda915cb7637439d484440d36be.jpg_600x330_0affc9e8.jpg">
      <div class="banner-info">
        <div class="banner-num">
          <span class="iconfont pic-icon">&#xe691;</span>
          13
          </div>
        <div class="banner-title">杭州云曼温泉</div>
      </div>
    </div>
    <common-gallery :imgs="imgs" v-show="showGallery" @close="closeGalleryClick"></common-gallery>
  </div>
</template>

<script>
import CommonGallery from 'common/gallery/Gallery'
export default {
  name: 'DetailBanner',
  data () {
    return {
      showGallery: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/201401/06/3fbbddda915cb7637439d484440d36be.jpg_r_800x800_c7fa6286.jpg', 'http://img1.qunarzz.com/sight/p0/1712/bd/bd818c6e984e8a48a3.img.jpg_r_800x800_8074e045.jpg', 'http://img1.qunarzz.com/sight/p0/1712/8b/8bef38042def436da3.img.jpg_r_800x800_9577a744.jpg']
    }
  },
  components: {
    CommonGallery
  },
  methods: {
    handleGalleryClick () {
      this.showGallery = true
    },
    closeGalleryClick () {
      this.showGallery = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position relative
    overflow hidden
    height 0
    padding-bottom 55%
    .banner-img
      width 100%
    .banner-info
      position absolute
      left 0
      right 0
      bottom 0
      line-height .6rem
      color #fff
      padding-left .2rem
      .banner-num
        padding 0 .2rem
        height .32rem
        width .8rem
        line-height .32rem
        border-radius .2rem
        background-color rgba(0, 0, 0, .5)
        font-size .24rem
        text-align center
        .pic-icon
          font-size .24rem
      .banner-title
        font-size .35rem
        padding-bottom .2rem
        background-image linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.5))
</style>
