<template>
  <div class="search">
    <!------搜索框----->
    <view class="search-box">
      <u-search v-model="searchValue"></u-search>
    </view>
    <!------搜索历史----->
    <view class="history-box" v-if="historyList.length !== 0">
      <view class="history-title">
        <title>搜索历史</title>
        <u-icon name="trash" size="32"></u-icon>
      </view>
      <!------标签列表区域----->
      <view class="history-list">
        <uni-tag
          v-text="item"
          v-for="(item, i) in historyList"
          :key="i"
          type="error"
          :circle="true"
        ></uni-tag>
        <uni-tag v-text="ree" text="标签" type="error" :circle="true"></uni-tag>
      </view>
    </view>
    <!------热门推荐----->
    <view class="history-box" v-if="hotList.length !== 0">
      <view class="history-title">
        <title>热门推荐</title>
        <u-icon name="trash" size="32"></u-icon>
      </view>
      <!------标签列表区域----->
      <view class="history-list">
        <uni-tag v-text="item" v-for="(item, i) in hotList" :key="i"></uni-tag>
      </view>
    </view>
  </div>
</template>

<script>
export default {
  components: {},
  data () {
    return {
      searchValue: 'eew',
      historyList: ['前端', 'vue', 'node', 'react'],
      hotList: ['前端', 'vue', 'node', 'react']
    }
  },
  computed: {},
  methods: {},
  watch: {},

  // 页面周期函数--监听页面加载
  onLoad () {},
  // 页面周期函数--监听页面初次渲染完成
  onReady () {},
  // 页面周期函数--监听页面显示(not-nvue)
  onShow () {},
  // 页面周期函数--监听页面隐藏
  onHide () {},
  // 页面周期函数--监听页面卸载
  onUnload () {},
  // 页面处理函数--监听用户下拉动作
  onPullDownRefresh () {
    uni.stopPullDownRefresh()
  },
  // 页面处理函数--监听用户上拉触底
  onReachBottom () {}
  // 页面处理函数--监听页面滚动(not-nvue)
  /* onPageScroll(event) {}, */
  // 页面处理函数--用户点击右上角分享
  /* onShareAppMessage(options) {}, */
}
</script>

<style lang="scss">
@import 'uview-ui/index.scss';

.test {
  color: red;
}
.bottom-line {
  position: fixed;
  bottom: -5px;
  left: 0;
  width: 100vw;
  height: 5px;
  box-shadow: 0 -5px 5px #0000000d;
  z-index: 999;
}
.search {
  padding: 24px;
}
.history-box {
  padding: 0 10rpx 50rpx;
  .history-title {
    display: flex;
    justify-content: space-between;
    align-content: center;
    height: 40px;
    font-size: 16px;
    font-weight: bold;
  }
  .history-list{
    display: flex;
    flex-wrap: wrap;
    ::v-deep .uni-tag {
      margin-top: 5px;
      margin-right: 5px;
      border-radius: 25rpx;
    }
  }
}
</style>
