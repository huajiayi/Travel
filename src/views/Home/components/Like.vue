<template>
  <home-sction titleImgSrc="http://img1.qunarzz.com/piao/fusion/1711/89/ebc329f16c55bb02.png"
               title="猜你喜欢">
    <div class="like-item border-bottom" v-for="item of likeItems" :key="item.id">
      <div class="like-img-container">
        <img class="like-img" :src="item.imgSrc">
        <div class="like-tag" v-if="item.tag === '可订明日'" style="background-image: url('https://img1.qunarzz.com/piao/fusion/1802/52/b9080e45b69b4f02.png')">{{ item.tag }}</div>
        <div class="like-tag" v-else style="background-image: url('https://img1.qunarzz.com/piao/fusion/1802/20/2ba6d10b17972e02.png')">{{ item.tag }}</div>
      </div>
      <div class="like-info">
        <div class="like-title">{{ item.title }}</div>
        <div class="like-comment">
          <starlevel :level="item.level"></starlevel>
          <span class="like-comment-num">{{ item.commentCount }}条评论</span>
        </div>
        <div class="like-price">
          <span class="rmb">¥</span>
          <span class="like-price-num">{{ item.price }}</span>起
          <span class="like-address">{{ item.address }}</span>
        </div>
        <div class="like-feature" v-if="item.feature !== ''">{{ item.feature }}</div>
      </div>
    </div>
  </home-sction>
</template>

<script>
import HomeSction from './Section'
import Starlevel from './Starlevel'

export default {
  name: 'Like',
  components: {
    HomeSction,
    Starlevel
  },
  props: {
    likeItems: Array
  }
}
</script>

<style lang="scss" scoped>
  .border-bottom::before {
    border-bottom: 1px solid #e0e0e0;
  }
  .like-item {
    position: relative;
    display: flex;
    padding: 20px 0px;
    margin-left: 20px;
    .like-img-container {
      float: left;
      width: 200px;
      height: 200px;
      .like-img {
        width: 200px;
        height: 200px;
      }
      .like-tag {
        position: absolute;
        top: 20px;
        left: 0;
        width: 102px;
        height: 38px;
        color: white;
        font-size: 20px;
        text-indent: 4px;
        line-height: 38px;
        background-size: 100%;
      }
    }
    .like-info {
      flex: 1;
      overflow: hidden;
      margin-left: 22px;
      .like-title {
        font-size: 32px;
        margin-top: 22px;
      }
      .like-comment {
        font-size: 24px;
        margin-top: 14px;
        &-num {
          color: #616161;
          margin-left: 40px;
        }
      }
      .like-price {
        position: relative;
        font-size: 24px;
        line-height: 40px;
        margin-top: 22px;
        .rmb {
          color: #ff8300;
        }
        .like-price-num {
          color: #ff8300;
          font-size: 40px;
        }
        .like-address {
          position: absolute;
          right: 40px;
          bottom: 0;
          color: #616161;
          font-size: 24px;
        }
      }
      .like-feature {
        color: #f55;
        font-size: 24px;
        margin-top: 48px;
      }
    }
  }
</style>
