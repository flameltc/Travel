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
        imgURL: 'http://img1.qunarzz.com/piao/fusion/1809/3b/7b654a05c9b61e02.jpg_750x200_eb04c4da.jpg'
      }, {
        ID: '002',
        imgURL: 'http://img1.qunarzz.com/piao/fusion/1809/6a/847ac7b98f10e202.jpg_750x200_f0593cb5.jpg'
      }, {
        ID: '003',
        imgURL: 'http://img1.qunarzz.com/piao/fusion/1809/f0/b39b64c33a62e002.jpg_750x200_3e961ce7.jpg'
      }, {
        ID: '004',
        imgURL: 'http://img1.qunarzz.com/piao/fusion/1809/86/deb33800de224c02.jpg_750x200_74fb795e.jpg'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff !important
  .wrapper
    width: 100%
    height: 27vw
    overflow: hidden
    // padding-bottom: 38%
    background: #eee
    .bg-swiper
      width: 100%
</style>
