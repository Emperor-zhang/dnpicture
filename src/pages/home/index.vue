<template>
  <view class="content">
    首页
    <view class="iconfont icon-shipin"></view>
    <uni-badge text="1"></uni-badge>
    <uni-badge text="2"
               type="success"
               @click="bindClick"></uni-badge>
    <uni-badge text="3"
               type="primary"
               :inverted="true"></uni-badge>
  </view>
</template>
<script>
import { uniBadge } from '@dcloudio/uni-ui'
export default {
  components: {
    uniBadge
  },
  methods: {
    change (e) {
      console.log(e);
    }
  },
  onLoad () {
    // 原生小程序API
    wx.request({
      url: 'https://api-hmugo-web.itheima.net/api/public/v1/categories',
      success (res) {
        console.log(res)
      }
    })
    // uniapp的api
    uni.request({
      url: 'https://api-hmugo-web.itheima.net/api/public/v1/categories'
    }).then(res => {
      console.log(res)
    })
  }
}
</script>
<style>
</style>