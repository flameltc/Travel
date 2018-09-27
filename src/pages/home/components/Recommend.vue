<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <img class="item-img" :src="item.imgURL">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-btn">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [{
        id: '0001',
        imgURL: 'http://img1.qunarzz.com/sight/p0/201401/06/3fbbddda915cb7637439d484440d36be.jpg_200x200_a54e87dd.jpg',
        title: '杭州云曼温泉',
        desc: '潮流电音、浪漫灯光、梦幻水舞百秀集结'
      }, {
        id: '0002',
        imgURL: 'http://img1.qunarzz.com/sight/p0/1508/12/4e6170303c63bdb7070fb1987480afab.water.jpg_200x200_0775a71c.jpg',
        title: '杭州极地海洋世界',
        desc: '潮流电音、浪漫灯光、梦幻水舞百秀集结'
      }, {
        id: '0003',
        imgURL: 'http://img1.qunarzz.com/sight/p0/1808/d6/d6c567a31d0a5462a3.img.jpg_200x200_fe329041.jpg',
        title: '千岛湖九龙溪漂流',
        desc: '潮流电音、浪漫灯光、梦幻水舞百秀集结'
      }, {
        id: '0004',
        imgURL: 'http://img1.qunarzz.com/sight/p0/1603/ae/aecef86d7655873f90.water.jpg_200x200_22a0790e.jpg',
        title: '杭州野生动物世界',
        desc: '潮流电音、浪漫灯光、梦幻水舞百秀集结'
      }, {
        id: '0005',
        imgURL: 'http://img1.qunarzz.com/sight/p0/1603/18/18ae748f826c5abe90.water.jpg_200x200_67503119.jpg',
        title: '大明山',
        desc: '潮流电音、浪漫灯光、梦幻水舞百秀集结'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .title
    background #eee
    line-height .8rem
    text-indent .3rem
    margin-top .1rem
  .item
    display flex
    height 1.9rem
    overflow hidden
    .item-img
      height 1.7rem
      width 1.7rem
      padding .1rem
    .item-info
      flex 1
      padding .1rem
      min-width 0
      .item-title
        line-height .54rem
        font-size .32rem
        ellipsis()
      .item-desc
        line-height .4rem
        color #ccc
        ellipsis()
      .item-btn
        margin-top .2rem
        border-radius .1rem
        background-color #ff9300
        padding 0 .1rem
        color #fff
</style>
