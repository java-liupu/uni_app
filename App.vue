<script setup>
  import { onLaunch, onShow, onError } from '@dcloudio/uni-app';
  import { ShoproInit } from './sheep';

  onLaunch(() => {
    // 延时隐藏原生导航栏
    setTimeout(() => {
      uni.hideTabBar();
    }, 200);

    // 加载Shopro底层依赖
    ShoproInit();
  });

  onShow((options) => {
    // #ifdef APP-PLUS
    // 获取urlSchemes参数
    const args = plus.runtime.arguments;
    if (args) {
    }

    // 获取剪贴板
    uni.getClipboardData({
      success: (res) => {},
    });
    // #endif

    // #ifdef MP-WEIXIN
    // 确认收货回调结果
    console.log(options, 'options');
    // #endif
  });
</script>

<style lang="scss">
  @import '@/sheep/scss/index.scss';
</style>
