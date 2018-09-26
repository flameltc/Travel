<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="item of swiperList" :key="item.ID">
        <img class="bg-swiper" :src="item.imgURL" />
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
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
        ID: '001',
        imgURL: 'https://imgs.qunarzz.com/vc/c4/38/76/284d1c5cd02b88a4cd7247b8e3.jpg_92.jpg'
      }, {
        ID: '002',
        imgURL: 'https://imgs.qunarzz.com/ftejia/1808/4a/2c3df86d3fc9ae.jpg'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff
  .wrapper
    width: 100%
    height: 25vw
    // overflow: hidden
    // padding-bottom: 38%
    background: #eee
    .bg-swiper
      width: 100%
</style>
