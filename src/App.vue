<template>
  <div>
    <router-view></router-view>
    <h1>黑马头条</h1>
    <div>
      <i class="toutiao icon-yuedu"></i>
    </div>
    <van-button type="primary">主要按钮</van-button>
    <van-button type="success">成功按钮</van-button>
    <van-button type="default">默认按钮</van-button>
    <van-button type="warning">警告按钮</van-button>
    <van-button type="danger">危险按钮</van-button>
  </div>

</template>

<script>
export default {
  name: 'App'
}
</script>

<style lang="less" scoped>
</style>
