<template>
  <demo-section class="demo-skeleton">
    <demo-block :title="t('basicUsage')">
      <van-skeleton title :row="3" />
    </demo-block>

    <demo-block :title="t('showAvatar')">
      <van-skeleton title avatar :row="3" />
    </demo-block>

    <demo-block :title="t('showChildren')">
      <switch :checked="show" @change="show=!show" size="24px" />
      <van-skeleton title avatar :row="3" :loading="!show">
        <div class="demo-preview">
          <img src="https://img01.yzcdn.cn/vant/logo.png" />
          <div class="demo-content">
            <h3>{{ t('title') }}</h3>
            <p>{{ t('desc') }}</p>
          </div>
        </div>
      </van-skeleton>
    </demo-block>
  </demo-section>
</template>

<script>
import { Skeleton } from 'vant'

export default {
  components: {
    'van-skeleton': Skeleton
  },
  i18n: {
    'zh-CN': {
      showAvatar: '显示头像',
      showChildren: '显示子组件',
      title: '关于 Vant',
      desc:
        'Vant 是一套轻量、可靠的移动端 Vue 组件库，提供了丰富的基础组件和业务组件，帮助开发者快速搭建移动应用。',
    },
    'en-US': {
      showAvatar: 'Show Avatar',
      showChildren: 'Show Children',
      title: 'About Vant',
      desc: 'Vant is a set of Mobile UI Components built on Vue.',
    },
  },
  data() {
    return {
      show: false,
    };
  },
};
</script>

<style lang="less">
@import '../../style/var';
.demo-skeleton {
  background-color: @white;
  .van-switch {
    margin: 0 @padding-md @padding-xs;
  }
  .demo-preview {
    display: flex;
    padding: 0 @padding-md;
    .demo-content {
      padding-top: 6px;
      h3 {
        margin: 0;
        font-size: 18px;
        line-height: 20px;
      }
      p {
        margin: 13px 0 0;
        font-size: 14px;
        line-height: 20px;
      }
    }
    img {
      flex-shrink: 0;
      width: 32px;
      height: 32px;
      margin-right: @padding-md;
    }
  }
}
</style>
