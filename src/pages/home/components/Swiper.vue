<template>
<div class="wrapper">
<swiper :options="swiperOption">
    <!-- slides -->
    <swiper-slide v-for="item of list" :key="item.id" v-if="show">
      <img class="swiper-img" :src="item.imgUrl"/>
    </swiper-slide>
    <!-- Optional controls -->
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
  data: function () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        autoplay: 1000,
        effect: 'fade'
      }
    }
  },
  computed: {
    show () {
      return this.list.length
    }
  }
}
</script>

<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active
      background: #fff
  .wrapper
    overflow: hidden
    width: 100%
    height: 0
    background: #eee
    padding-bottom: 26.6%
    .swiper-img
      width: 100%
</style>
