<template>
  <demo-section class="demo-checkbox">
    <demo-block :title="t('basicUsage')">
      <van-checkbox v-model="checkbox1">{{ t('checkbox') }}</van-checkbox>
    </demo-block>

    <demo-block :title="t('disabled')">
      <van-checkbox :value="false" disabled>
        {{ t('checkbox') }}
      </van-checkbox>
      <van-checkbox :value="true" disabled>
        {{ t('checkbox') }}
      </van-checkbox>
    </demo-block>

    <demo-block :title="t('customShape')">
      <van-checkbox v-model="checkboxShape" shape="square">
        {{ t('customColor') }}
      </van-checkbox>
    </demo-block>

    <demo-block :title="t('customColor')">
      <van-checkbox v-model="checkbox2" checked-color="#ee0a24">
        {{ t('customColor') }}
      </van-checkbox>
    </demo-block>

    <demo-block :title="t('customIconSize')">
      <van-checkbox v-model="checboxIcon" icon-size="24px">
        {{ t('customIconSize') }}
      </van-checkbox>
    </demo-block>

    <demo-block :title="t('customIcon')">
      <van-checkbox v-model="checkbox3">
        {{ t('customIcon') }}
        <template #icon="{ checked }">
          <img :src="checked ? activeIcon : inactiveIcon" width="50rpx" height="40rpx"/>
        </template>
      </van-checkbox>
    </demo-block>

    <demo-block :title="t('disableLabel')">
      <van-checkbox v-model="checkboxLabel" label-disabled>
        {{ t('checkbox') }}
      </van-checkbox>
    </demo-block>

    <demo-block :title="t('title3')">
      <van-checkbox-group v-model="result">
        <van-checkbox name="a">{{ t('checkbox') }} a</van-checkbox>
        <van-checkbox name="b">{{ t('checkbox') }} b</van-checkbox>
      </van-checkbox-group>
    </demo-block>

    <demo-block v-if="!isWeapp" :title="t('horizontal')">
      <van-checkbox-group v-model="horizontalResult" direction="horizontal">
        <van-checkbox name="a">{{ t('checkbox') }} a</van-checkbox>
        <van-checkbox name="b">{{ t('checkbox') }} b</van-checkbox>
      </van-checkbox-group>
    </demo-block>

    <demo-block :title="t('title4')">
      <van-checkbox-group v-model="result2" :max="2">
        <van-checkbox name="a">{{ t('checkbox') }} a</van-checkbox>
        <van-checkbox name="b">{{ t('checkbox') }} b</van-checkbox>
        <van-checkbox name="c">{{ t('checkbox') }} c</van-checkbox>
      </van-checkbox-group>
    </demo-block>

    <demo-block v-if="!isWeapp" :title="t('toggleAll')">
      <van-checkbox-group v-model="checkAllResult" ref="group">
        <van-checkbox name="a">{{ t('checkbox') }} a</van-checkbox>
        <van-checkbox name="b">{{ t('checkbox') }} b</van-checkbox>
        <van-checkbox name="c">{{ t('checkbox') }} c</van-checkbox>
      </van-checkbox-group>

      <div class="demo-checkbox-buttons">
        <van-button type="primary" @click="checkAll">
          {{ t('checkAll') }}
        </van-button>
        <van-button type="info" @click="toggleAll">
          {{ t('inverse') }}
        </van-button>
      </div>
    </demo-block>

    <demo-block :title="t('title5')">
      <van-checkbox-group v-model="result3">
        <van-cell-group>
          <van-cell
            v-for="(item, index) in list"
            clickable
            :key="index"
            :title="`${t('checkbox')} ${item}`"
            @click="toggle(index)"
          >
            <template #right-icon>
              <van-checkbox ref="checkboxes" :name="item" />
            </template>
          </van-cell>
        </van-cell-group>
      </van-checkbox-group>
    </demo-block>
  </demo-section>
</template>

<script>
import { Button, Cell, CellGroup, Checkbox, CheckboxGroup } from 'vant'

export default {
  components: {
    'van-cell': Cell,
    'van-cell-group': CellGroup,
    'van-checkbox': Checkbox,
    'van-checkbox-group': CheckboxGroup,
    'van-button': Button
  },
  i18n: {
    'zh-CN': {
      checkbox: '复选框',
      customIcon: '自定义图标',
      customIconSize: '自定义大小',
      customColor: '自定义颜色',
      customShape: '自定义形状',
      title3: '复选框组',
      title4: '限制最大可选数',
      title5: '搭配单元格组件使用',
      toggleAll: '全选与反选',
      checkAll: '全选',
      inverse: '反选',
      horizontal: '水平排列',
      disableLabel: '禁用文本点击',
    },
    'en-US': {
      checkbox: 'Checkbox',
      customIcon: 'Custom Icon',
      customIconSize: 'Custom Icon Size',
      customColor: 'Custom Color',
      customShape: 'Custom Shape',
      title3: 'Checkbox Group',
      title4: 'Maximum amount of checked options',
      title5: 'Inside a Cell',
      toggleAll: 'Toggle All',
      checkAll: 'Check All',
      inverse: 'Inverse',
      horizontal: 'Horizontal',
      disableLabel: 'Disable label click',
    },
  },
  data() {
    return {
      checkbox1: true,
      checkbox2: true,
      checkbox3: true,
      checkboxShape: true,
      checkboxLabel: true,
      checboxIcon: true,
      list: ['a', 'b'],
      result: ['a', 'b'],
      result2: [],
      result3: [],
      checkAllResult: [],
      horizontalResult: [],
      activeIcon: 'https://img01.yzcdn.cn/vant/user-active.png',
      inactiveIcon: 'https://img01.yzcdn.cn/vant/user-inactive.png',
    };
  },
  methods: {
    toggle(index) {
      this.$refs.checkboxes[index].toggle();
    },
    checkAll() {
      this.$refs.group.toggleAll(true);
    },
    toggleAll() {
      this.$refs.group.toggleAll();
    },
  },
};
</script>

<style lang="less">
@import '../../style/var';
.demo-checkbox {
  background: @white;
  .van-checkbox {
    margin: 0 0 8px 20px;
  }
  .van-cell {
    .van-checkbox {
      margin: 0;
    }
  }
  img {
    height: 20px;
  }
  &-buttons {
    margin-top: @padding-md;
    .van-button {
      margin-left: @padding-md;
    }
  }
  .van-doc-demo-block__title {
    margin-top: -8px;
  }
}
</style>
