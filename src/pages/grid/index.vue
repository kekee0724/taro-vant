<template>
  <demo-section class="demo-grid">
    <demo-block :title="t('basicUsage')">
      <van-grid>
        <van-grid-item
          v-for="i in 4"
          :key="i"
          icon="photo-o"
          :text="t('text')"
        />
      </van-grid>
    </demo-block>

    <demo-block :title="t('columnNum')">
      <van-grid :column-num="3">
        <van-grid-item
          v-for="i in 6"
          :key="i"
          icon="photo-o"
          :text="t('text')"
        />
      </van-grid>
    </demo-block>

    <demo-block :title="t('customContent')">
      <van-grid :border="false" :column-num="3">
        <van-grid-item>
          <van-image
            fit="contain"
            src="https://img01.yzcdn.cn/vant/apple-1.jpg"
            width="218rpx"
            height="177rpx"
          />
        </van-grid-item>
        <van-grid-item>
          <van-image
            fit="contain"
            src="https://img01.yzcdn.cn/vant/apple-2.jpg"
            width="218rpx"
            height="177rpx"
          />
        </van-grid-item>
        <van-grid-item>
          <van-image
            fit="contain"
            src="https://img01.yzcdn.cn/vant/apple-3.jpg"
            width="218rpx"
            height="177rpx"
          />
        </van-grid-item>
      </van-grid>
    </demo-block>

    <demo-block :title="t('square')">
      <van-grid square>
        <van-grid-item
          v-for="i in 8"
          :key="i"
          icon="photo-o"
          :text="t('text')"
        />
      </van-grid>
    </demo-block>

    <demo-block :title="t('gutter')">
      <van-grid :gutter="10">
        <van-grid-item
          v-for="i in 8"
          :key="i"
          icon="photo-o"
          :text="t('text')"
        />
      </van-grid>
    </demo-block>

    <demo-block :title="t('horizontal')">
      <van-grid direction="horizontal" :column-num="3">
        <van-grid-item icon="photo-o" :text="t('text')" />
        <van-grid-item icon="photo-o" :text="t('text')" />
        <van-grid-item icon="photo-o" :text="t('text')" />
      </van-grid>
    </demo-block>

    <demo-block :title="t('route')">
      <van-grid clickable :column-num="2">
        <van-grid-item icon="home-o" :text="t('vueRoute')" to="/" />
        <van-grid-item
          icon="search"
          :text="t('urlRoute')"
          url="/vant/mobile.html"
        />
      </van-grid>
    </demo-block>

    <demo-block :title="t('showBadge')">
      <van-grid :column-num="2">
        <van-grid-item icon="home-o" :text="t('text')" dot />
        <van-grid-item icon="search" :text="t('text')" badge="99+" />
      </van-grid>
    </demo-block>
  </demo-section>
</template>

<script>
import { Grid, GridItem, Image } from 'vant'

export default {
  components: {
    'van-grid': Grid,
    'van-grid-item': GridItem,
    'van-image': Image
  },
  i18n: {
    'zh-CN': {
      text: '文字',
      route: '页面导航',
      gutter: '格子间距',
      square: '正方形格子',
      columnNum: '自定义列数',
      customContent: '自定义内容',
      urlRoute: 'URL 跳转',
      vueRoute: '路由跳转',
      showBadge: '徽标提示',
      horizontal: '内容横排',
    },
    'en-US': {
      text: 'Text',
      route: 'Route',
      gutter: 'Gutter',
      square: 'Square',
      columnNum: 'Column Num',
      customContent: 'Custom Content',
      urlRoute: 'URL',
      vueRoute: 'Vue Router',
      showBadge: 'Show Badge',
      horizontal: 'Horizontal',
    },
  },
};
</script>

<style lang="less">
@import '../../style/var';
</style>
