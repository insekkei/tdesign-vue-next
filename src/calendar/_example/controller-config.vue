<template>
  <t-space class="controllerConfig-demo" direction="vertical">
    <template v-if="controllerConfig">
      <fieldset>
        <legend>控件全局</legend>
        <t-space direction="vertical">
          <p>
            <label>是否显示（全部控件）：</label>
            <t-switch v-model="controllerConfig.visible" />
          </p>
          <p>
            <label>是否禁用（全部控件）：</label>
            <t-switch v-model="controllerConfig.disabled" />
          </p>
        </t-space>
      </fieldset>

      <fieldset>
        <legend>控件局部</legend>
        <t-space direction="vertical">
          <t-space break-line>
            <p>
              <label>是否显示“模式切换”控件：</label>
              <t-switch v-model="controllerConfig.mode.visible" />
            </p>
            <p>
              <label>是否禁用“模式切换”控件：</label>
              <t-switch v-model="controllerConfig.mode.radioGroupProps.disabled" />
            </p>
          </t-space>

          <t-space break-line>
            <p>
              <label>是否显示“年份选择”控件：</label>
              <t-switch v-model="controllerConfig.year.visible" />
            </p>
            <p>
              <label>是否禁用“年份选择”控件：</label>
              <t-switch v-model="controllerConfig.year.selectProps.disabled" />
            </p>
          </t-space>

          <t-space break-line>
            <p>
              <label>是否显示“月份选择”控件：</label>
              <t-switch v-model="controllerConfig.month.visible" />
            </p>
            <p>
              <label>是否禁用“月份选择”控件：</label>
              <t-switch v-model="controllerConfig.month.selectProps.disabled" />
            </p>
          </t-space>

          <t-space break-line>
            <p>
              <label>是否禁用“隐藏周末”控件：</label>
              <t-switch v-model="controllerConfig.weekend.hideWeekendButtonProps.disabled" />
            </p>
            <p>
              <label>是否禁用“显示周末”控件：</label>
              <t-switch v-model="controllerConfig.weekend.showWeekendButtonProps.disabled" />
            </p>
            <p>
              <label>是否显示“隐藏\显示周末”控件：</label>
              <t-switch v-model="controllerConfig.weekend.visible" />
            </p>
          </t-space>

          <t-space break-line>
            <p>
              <label>是否禁用“今天”按钮控件：</label>
              <t-switch v-model="controllerConfig.current.currentDayButtonProps.disabled" />
            </p>
            <p>
              <label>是否禁用“本月”按钮控件：</label>
              <t-switch v-model="controllerConfig.current.currentMonthButtonProps.disabled" />
            </p>
            <p>
              <label>是否显示“今天\本月”控件：</label>
              <t-switch v-model="controllerConfig.current.visible" />
            </p>
          </t-space>
        </t-space>
      </fieldset>
    </template>
    <t-calendar :controller-config="controllerConfig.visible ? controllerConfig : false" />
  </t-space>
</template>

<script setup>
import { reactive } from 'vue';

const controllerConfig = reactive({
  visible: true,
  disabled: false, // 是否禁用（全部控件）
  // 年份选择框组件相关设置
  year: {
    visible: true, // 是否显示
    selectProps: {
      // 用于透传props给该select组件
      disabled: false,
      size: 'small',
    },
  },
  // 月份选择框组件相关设置
  month: {
    visible: true, // 是否显示（“year”模式下本身是不显示该组件的）
    selectProps: {
      // 用于透传props给该select组件
      disabled: false,
      size: 'small',
    },
  },
  // 模式切换单选组件设置
  mode: {
    visible: true, // 是否显示
    radioGroupProps: {
      disabled: false,
      size: 'small',
    },
  },
  // 隐藏\显示周末按钮组件相关设置
  weekend: {
    visible: true, // 是否显示
    showWeekendButtonProps: {
      // 用于透传props给显示周末按钮组件
      disabled: false,
      size: 'small',
    },
    hideWeekendButtonProps: {
      // 用于透传props给隐藏周末按钮组件
      disabled: false,
      variant: 'base',
      size: 'small',
    },
  },
  // “今天\本月”按钮组件相关设置
  current: {
    visible: true, // 是否显示
    currentDayButtonProps: {
      // 用于透传props给“今天”钮组件（“month”模式下有效）
      disabled: false,
      size: 'small',
      theme: 'warning',
    },
    currentMonthButtonProps: {
      // 用于透传props给“本月”按钮组件（“year”模式下有效）
      disabled: false,
      size: 'small',
      theme: 'success',
    },
  },
});
</script>

<style scoped>
.controllerConfig-demo fieldset {
  border: solid 1px #eee;
  padding: 10px 20px;
}
.controllerConfig-demo fieldset legend {
  margin-left: 20px;
  padding: 0 10px;
}
</style>
