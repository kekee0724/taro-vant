<template>
  <demo-section class="demo-overlay">
    <demo-block :title="t('basicUsage')">
      <van-button
        type="primary"
        :text="t('showOverlay')"
        style="margin-left: 16px;"
        @click="show = true"
      />

      <van-overlay :show="show" @click="show = false" duration="0.5"/>
    </demo-block>

    <demo-block :title="t('embeddedContent')">
      <van-button
        type="primary"
        :text="t('embeddedContent')"
        style="margin-left: 16px;"
        @click="showEmbedded = true"
      />

      <van-overlay :show="showEmbedded" @click="showEmbedded = false" duration="0.5">
        <div class="wrapper">
          <div class="block" />
        </div>
      </van-overlay>
    </demo-block>
  </demo-section>
</template>

<script>
import { Button, Overlay } from 'vant'

export default {
  components: {
    'van-overlay': Overlay,
    'van-button': Button
  },
  i18n: {
    'zh-CN': {
      showOverlay: '显示遮罩层',
      embeddedContent: '嵌入内容',
    },
    'en-US': {
      showOverlay: 'Show Overlay',
      embeddedContent: 'Embedded Content',
    },
  },
  data() {
    return {
      show: false,
      showEmbedded: false,
    };
  },
};
</script>

<style lang="less">
@import '../../style/var';
.demo-overlay {
  background: @white;
  .wrapper {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100%;
  }
  .block {
    width: 120px;
    height: 120px;
    background-color: @white;
  }
}
</style>
