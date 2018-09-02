<template>
  <swiper :options="swiperOption" ref="mySwiper">
    <!-- slides -->
    <swiper-slide v-for="(page, index) of categoryPages" :key="index">
      <div class="category-item" v-for="category of page" :key="category.id">
        <img class="category-img" :src="category.src">
        <span class="category-keyword">{{ category.keyword }}</span>
      </div>
    </swiper-slide>
    <!-- Optional controls -->
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
</template>

<script>
export default {
  name: 'HomeCategory',
  props: {
    categorys: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: {
          el: '.swiper-pagination'
        }
      }
    }
  },
  computed: {
    categoryPages () {
      let categoryPages = []
      this.categorys.forEach((item, index) => {
        let page = Math.floor(index / 8)
        if (!categoryPages[page]) {
          categoryPages[page] = []
        }
        categoryPages[page].push(item)
      })

      return categoryPages
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
  background-color: rgba(0,175,190,.8) !important;
  }
</style>

<style lang="scss" scoped>
  .swiper-container {
    height: 400px;
    .category-item {
      float: left;
      width: 25%;
      height: 150px;
      margin-top: 20px;
      text-align: center;
      .category-img {
        height: auto;
        width: 110px;
      }
      .category-keyword {
        display: block;
        font-size: 28px;
      }
    }
  }
</style>
