<template>
  <swiper :options="swiperOption" ref="mySwiper">
    <!-- slides -->
    <swiper-slide v-for="img of swiperImgs" :key="img.id">
      <img class="swiper-img" :src="img.src">
    </swiper-slide>
    <!-- Optional controls -->
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    swiperImgs: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: {
          el: '.swiper-pagination'
        },
        autoplay: true,
        loop: true
      }
    }
  }
}
</script>

<style>
  .swiper-container .swiper-pagination-bullet {
    width: 12px;
    height: 12px;
  }
  .swiper-container .swiper-pagination-bullet-active {
    background-color: white !important;
  }
</style>

<style lang='scss' scoped>
  .swiper-container {
    height: 200px;
    .swiper-img {
      height: 200px;
    }
  }
</style>
