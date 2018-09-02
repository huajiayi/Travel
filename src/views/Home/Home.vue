<template>
    <div>
      <home-header></home-header>
      <home-swiper :swiperImgs="swiperImgs"></home-swiper>
      <home-category :categorys="categorys"></home-category>
      <div class="split-line"></div>
      <div class="activity-item">
        <img class="activity-img" src="http://img1.qunarzz.com/piao/fusion/1806/29/30427c0e0658b502.png">
      </div>
      <div class="split-line"></div>
      <hot-sale :hotSaleItems="hotSaleItems"></hot-sale>
      <div class="split-line"></div>
      <like :likeItems="likeItems"></like>
      <weekend-play :productionItems="productionItems"></weekend-play>
    </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeCategory from './components/Category'
import HotSale from './components/HotSale'
import Like from './components/Like'
import WeekendPlay from './components/WeekendPlay'

export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeCategory,
    HotSale,
    Like,
    WeekendPlay
  },
  data () {
    return {
      swiperImgs: [],
      categorys: [],
      hotSaleItems: [],
      likeItems: [],
      productionItems: []
    }
  },
  created () {
    this.axios.get('Travel/dist/mock/homeData.json').then(res => {
      let { data } = res
      // $data里的key和json里的key相同，所以这里简化了操作
      Object.keys(this.$data).forEach(key => {
        this[key] = data[key]
      })
    }).catch(err => {
      console.log(err)
    })
  }
}
</script>

<style lang='scss' scoped>
  .split-line {
    height: 16px;
    background-color: #f5f5f5;
  }
  .activity-item {
    width: 100%;
    text-align: center;
    .activity-img {
      height: 200px;
    }
  }
</style>
