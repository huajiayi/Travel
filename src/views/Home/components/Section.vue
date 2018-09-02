<template>
  <div class="section-group">
    <div class="section-group-title">
      <img class="title-img" :src="titleImgSrc">
      <h2 class="title">{{ title }}</h2>
      <div class="title-more" v-if="titleMore">
        <span>{{ titleMore }}</span>
        <span class="iconfont icon-more"></span>
      </div>
    </div>
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'HomeSection',
  props: {
    titleImgSrc: String,
    title: String,
    titleMore: String
  }
}
</script>

<style lang="scss">
  $titleHeight: 48px;

  .section-group {
    margin: 20px 0px;
    &-title {
      height: $titleHeight;
      .title-img {
        width: 30px;
        height: 30px;
        line-height: $titleHeight;
        margin: 0px 10px 0px 20px;
      }
      .title {
        display: inline;
        font-size: 32px;
        font-weight: normal;
        line-height: $titleHeight;
      }
      .title-more {
        float: right;
        font-size: 24px;
        line-height: $titleHeight;
        color: #616161;
        margin-right: 32px;
      }
    }
  }
</style>
