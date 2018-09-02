<template>
  <div class="starlevel">
    <span class="iconfont icon-star" v-for="num of star" :key="num"></span>
    <span class="iconfont icon-half-star" v-if="hasHalfStar"></span>
  </div>
</template>

<script>
export default {
  name: 'Starlevel',
  props: {
    level: Number
  },
  computed: {
    star () {
      return Math.floor(this.level)
    },
    hasHalfStar () {
      return ~~this.level !== this.level
    }
  }
}
</script>

<style lang="scss" scoped>
  .starlevel {
    display: inline;
    .iconfont {
      color: #ffb436;
      font-size: 24px;
    }
  }
</style>
