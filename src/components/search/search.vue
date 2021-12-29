<template>
  <view class="search" :style="{ 'padding-top': barHeight + 'px' }"
  @click="$emit('click')">
    <view class="search-box">
      <u-icon class="icon" name="search" color="#ccc" size="28"></u-icon>
      <text>搜索社区内容</text>
    </view>
  </view>
</template>

<script>
export default {
  props: {},
  data: () => ({
    barHeight: 0
  }),
  computed: {},
  beforeMount () {
    this.getNavBarHeight()
  },
  methods: {
    getNavBarHeight () {
      uni.getSystemInfo({
        success: result => {
          console.log(result)
          this.barHeight = result.statusBarHeight
        },
        fail: error => {
          console.log(error)
        }
      })
    },
    click () {
      console.log(123)
    }
  },
  watch: {},

  // 组件周期函数--监听组件挂载完毕
  mounted () {},
  // 组件周期函数--监听组件数据更新之前
  beforeUpdate () {},
  // 组件周期函数--监听组件数据更新之后
  updated () {},
  // 组件周期函数--监听组件激活(显示)
  activated () {},
  // 组件周期函数--监听组件停用(隐藏)
  deactivated () {},
  // 组件周期函数--监听组件销毁之前
  beforeDestroy () {}
}
</script>

<style lang="scss">
.search {
  position: relative;
  width: 100vw;
  background: #fff;
  padding: 0 32rppx 12 rpx;
  z-index: 999;
  display: flex;
  justify-content: flex-start;
  color: #ccc;
  align-items: center;
  .search-box {
    position: relative;
    display: flex;
    justify-content: flex-start;
    width: 60%;
    @media screen and (max-width: 320px) {
      width: 50%;
    }
    background: #f3f3f3;
    height: 64rpx;
    border-radius: 32rpx;
    line-height: 64rpx;
    columns: #ccc;
    font-size: 26rpx;
    padding-left: 74rpx;
  }
  .icon{
    position: absolute;
    left: 32px;
    top: 19px;
  }
}
</style>
