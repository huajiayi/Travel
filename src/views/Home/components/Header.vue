<template>
  <div class="header">
      <div class="header-left">
          <span class="iconfont icon-back"></span>
      </div>
      <div class="header-input">
          <span class="iconfont icon-search"></span>
          <input class="search-input" type="text" placeholder="请输入城市/景点/游玩主题">
      </div>
      <div class="header-right">
          <span class="city">黑龙江</span>
          <span class="iconfont icon-select-down"></span>
      </div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang="scss" scoped>
  .header {
    display: flex;
    width: 100%;
    height: 80px;
    background-color: #00bcd4;
    color: white;
    .icon-font {
      font-size: 32px;
      font-weight: bold;
    }
    .header-left {
      float: left;
      width: 64px;
      line-height: 80px;
      text-align: center;
    }
    .header-input {
        flex: 1;
        height: 56px;
        margin: 13px;
        border-radius: 8px;
        background-color: white;
        line-height: 56px;
        color: #ccc;
        .icon-search {
          margin: 0px 10px;
          font-size: 28px;
        }
        .search-input {
            width: 440px;
            border: 0px;
            font-size: 28px;
            color: black;
            &::-webkit-input-placeholder {
                font-size: 28px;
                color: #ccc;
            }
        }
    }
    .header-right {
      float: right;
      width: 140px;
      line-height: 80px;
      text-align: center;
      .city {
          font-size: 28px;
      }
    }
  }
</style>
