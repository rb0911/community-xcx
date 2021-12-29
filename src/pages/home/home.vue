<template>
  <view class="home">
    <view class="search" :style="{'padding-top': barHeight + 'px'}">
      <!-- <u-search placeholder="日照香炉生紫烟" v-model="keyword"></u-search> -->
      <search @click="handle()"></search>
      <u-tabs name="list" :list="list" :is-scroll="false" :current="current" @change="change"></u-tabs>
    </view>
    <view class="bottom-line"></view>
  </view>
</template>

<script>
import search from '../../components/search/search.vue'

export default {
  components: {
    search
  },
  data: () => ({
    barHeight: 0,
    list: [
      {
        key: '',
        name: '首页'
      },
      {
        key: 'ask',
        name: '提问'
      },
      {
        key: 'share',
        name: '分享'
      },
      {
        key: 'discuss',
        name: '讨论'
      },
      {
        key: 'advise',
        name: '建议1'
      },
      {
        key: 'share1',
        name: '分享2'
      },
      {
        key: 'discuss1',
        name: '讨论1'
      },
      {
        key: 'advise1',
        name: '建议1'
      }
    ]
  }),
  computed: {},
  beforeMount () {
    this.getNavBarHeight()
  },
  methods: {
    getNavBarHeight () {
      uni.getSystemInfo({
        success: (result) => {
          console.log(result)
          this.barHeight = result.statusBarHeight - 30
        },
        fail: (error) => {
          console.log(error)
        }
      })
    },
    handle () {
      console.log(321)
      uni.navigateTo({
        url: '/subcom-pkg/search/search'
      })
    }
  },
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
.search {
  width: 70%;
}
</style>
