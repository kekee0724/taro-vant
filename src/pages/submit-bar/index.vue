<template>
  <demo-section class="demo-submit-bar">
    <demo-block :title="t('basicUsage')">
      <van-submit-bar
        :price="3050"
        :button-text="t('submit')"
        @submit="onClickButton"
      />
    </demo-block>

    <demo-block :title="t('disabled')">
      <van-submit-bar
        disabled
        :price="3050"
        :button-text="t('submit')"
        :tip="t('tip1')"
        tip-icon="info-o"
        @submit="onClickButton"
      />
    </demo-block>

    <!-- <demo-block :title="t('loadingStatus')">
      <van-submit-bar
        loading
        :price="3050"
        :button-text="t('submit')"
        @submit="onClickButton"
      />
    </demo-block> -->

    <demo-block :title="t('advancedUsage')">
      <van-submit-bar
        :price="3050"
        :button-text="t('submit')"
        @submit="onClickButton"
      >
        <van-checkbox v-model="checked">{{ t('check') }}</van-checkbox>
        <template #tip>
          {{ t('tip2') }}
          <span class="edit-address" @click="onClickLink">
            {{ t('tip3') }}
          </span>
        </template>
      </van-submit-bar>
    </demo-block>
  </demo-section>
</template>

<script>
import Taro from '@tarojs/taro'
import { Checkbox, SubmitBar } from 'vant'

export default {
  components: {
    'van-submit-bar': SubmitBar,
    'van-checkbox': Checkbox
  },
  i18n: {
    'zh-CN': {
      submit: '提交订单',
      tip1: '你的收货地址不支持同城送, 我们已为你推荐快递',
      tip2: '你的收货地址不支持同城送, ',
      tip3: '修改地址',
      check: '全选',
      clickButton: '点击按钮',
      clickLink: '修改地址',
    },
    'en-US': {
      submit: 'Submit',
      tip1: 'Some tips',
      tip2: 'Some tips, ',
      tip3: 'Link',
      check: 'Label',
      clickButton: 'Click button',
      clickLink: 'Click Link',
    },
  },
  data() {
    return {
      checked: true,
    };
  },
  methods: {
    onClickButton() {
      Taro.showToast({
        title: 'clickButton'
      })
    },
    onClickLink() {
      Taro.showToast({
        title: 'clickLink'
      })
    },
  },
};
</script>

<style lang="less">
@import '../../style/var';
.demo-submit-bar {
  .van-submit-bar {
    position: relative;
    padding-bottom: 0;
  }
  .edit-address {
    color: @blue;
  }
  .van-checkbox {
    margin-right: @padding-sm;
  }
}
</style>
