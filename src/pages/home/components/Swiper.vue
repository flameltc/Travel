<template>
  <div class="wrapper">
    <swiper :options="swiperOption" v-if="swiperShow">
      <swiper-slide v-for="item of list" :key="item.id">
        <img class="bg-swiper" :src="item.imgUrl" />
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      }
    }
  },
  computed: {
    swiperShow () {
      return this.list.length
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
