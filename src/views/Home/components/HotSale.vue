<template>
  <home-section titleImgSrc="http://img1.qunarzz.com/piao/fusion/1711/16/bfbb9874e8f11402.png"
                title="本周热门榜单" titleMore="全部榜单">
    <swiper :options="swiperOption" ref="mySwiper">
      <!-- slides -->
      <swiper-slide v-for="item of hotSaleItems" :key="item.rank">
        <div class="hotsale-item-group-img">
          <img class="hotsale-item-tag" v-if="+item.rank <= 3" :src="rankImgs[+item.rank - 1]">
          <img class="hotsale-item-img" :src="item.imgSrc">
        </div>
        <span class="hotsale-item-name">{{ item.name }}</span>
        <div class="hotsale-item-price">
          <span class="rmb">¥</span>
          <span class="price-num">{{ item.price }}</span>起
        </div>
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-scrollbar" slot="scrollbar"></div>
    </swiper>
  </home-section>
</template>

<script>
import HomeSection from './Section'

export default {
  name: 'HotSale',
  components: {
    HomeSection
  },
  props: {
    hotSaleItems: Array
  },
  data () {
    return {
      swiperOption: {
        slidesPerView: 3.5,
        slidesOffsetBefore: 10,
        slidesOffsetAfter: 10,
        scrollbar: {
          el: '.swiper-scrollbar',
          hide: true
        }
      },
      rankImgs: [
        'http://img1.qunarzz.com/piao/fusion/1710/ab/159673b63e6ca702.png',
        'http://img1.qunarzz.com/piao/fusion/1710/2d/36d0c4adaebbbc02.png',
        'http://img1.qunarzz.com/piao/fusion/1710/67/edc47ffef9e96b02.png'
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
  .swiper-container {
    width: 100%;
    height: 300px;
    margin-top: 20px;
    text-align: center;
    .hotsale-item-group-img {
      position: relative;
      .hotsale-item-tag {
        position: absolute;
        left: 6px;
        width: 84px;
        height: 40px;
      }
      .hotsale-item-img {
        height: 200px;
        margin-top: 5px;
      }
    }
    .hotsale-item-name {
      display: block;
      font-size: 24px;
    }
    .hotsale-item-price {
      display: block;
      font-size: 24px;
      .rmb {
        color: #ff8300;
      }
      .price-num {
        color: #ff8300;
        font-size: 28px;
      }
    }
  }
</style>
