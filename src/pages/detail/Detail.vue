<template>
  <div>
    <detail-banner :sightName="sightName" :bannerImg="bannerImg" :galleryImgs="galleryImgs"></detail-banner>
    <detail-header></detail-header>
    <div class="content"></div>
  </div>
</template>

<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import axios from 'axios'
export default {
  name: 'detail',
  components: {
    DetailBanner,
    DetailHeader
  },
  data () {
    return {
      sightName: '',
      bannerImg: '',
      galleryImgs: [],
      lastSightName: ''
    }
  },
  methods: {
    getDetailInfo () {
      axios.get('/api/detail.json', {
        params: {
          id: this.$route.params.id
        }
      }).then(this.handleGetDataSucc)
    },
    handleGetDataSucc (res) {
      res = res.data
      if (res.data && res.data) {
        const data = res.data
        this.sightName = data.sightName
        this.bannerImg = data.bannerImg
        this.galleryImgs = data.galleryImgs
      }
    }
  },
  mounted () {
    this.getDetailInfo()
    this.lastSightName = this.sightName
  },
  activated () {
    if (this.lastSightName !== this.sightName) {
      this.getDetailInfo()
      this.lastSightName = this.sightName
    }
  }
}
</script>

<style lang="stylus" scoped>
  .content
    height 50rem
</style>
