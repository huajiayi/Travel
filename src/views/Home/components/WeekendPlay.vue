<template>
  <div>
    <div class="title-warpper">
      <h2 class="title">周末去哪儿</h2>
    </div>
    <div v-for="item of productionItems" :key="item.id">
      <img class="production-img" :src="item.src">
      <div class="production-info" >
        <p class="production-name">{{ item.name }}</p>
        <p class="production-desc">{{ item.desc }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'WeekendPlay',
  props: {
    productionItems: Array
  }
}
</script>

<style lang="scss" scoped>
  .title-warpper {
    height: 80px;
    background-color: #f5f5f5;
    .title {
      color: #212121;
      font-size: 30px;
      line-height: 80px;
      font-weight: normal;
      margin-left: 26px;
    }
  }
  .production-img {
    width: 100%;
    height: auto;
  }
  .production-info {
    padding: 14px 20px 20px 20px;
    .production-name {
      font-size: 36px;
    }
    .production-desc {
      color: #616161;
      font-size: 28px;
      margin-top: 10px;
    }
  }
</style>
