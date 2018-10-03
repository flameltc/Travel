<template>
  <div>
    <div class="banner" @click="handleGalleryClick">
      <img class="banner-img" :src="bannerImg">
      <div class="banner-info">
        <div class="banner-num">
          <span class="iconfont pic-icon">&#xe691;</span>
          {{ this.galleryImgs.length }}
          </div>
        <div class="banner-title">{{ this.sightName }}</div>
      </div>
    </div>
    <fade-animation>
      <common-gallery :imgs="galleryImgs" v-show="showGallery" @close="closeGalleryClick"></common-gallery>
    </fade-animation>
  </div>
</template>

<script>
import CommonGallery from 'common/gallery/Gallery'
import FadeAnimation from 'common/fadeAnimation/Fade'
export default {
  name: 'DetailBanner',
  props: {
    sightName: String,
    bannerImg: String,
    galleryImgs: Array
  },
  data () {
    return {
      showGallery: false
    }
  },
  components: {
    CommonGallery,
    FadeAnimation
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
