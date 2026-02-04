title: Slider组件
description: Slider滑块组件的用途、默认参数和可配置项说明
keywords: Slider,滑块,输入型组件,组件配置
category: 组件菜单类
---
# Slider 滑块

## 组件用途
Slider 是输入型组件，通过拖动滑块在一个固定区间内进行选择。支持单值选择和范围选择。
- **数值选择** - 在固定区间内选择数值
- **范围选择** - 选择一个数值范围
- **音量调节** - 调节音量、亮度等连续值

## 默认配置
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: '',
  type: 'Inputer',
  label: '新建滑块按钮',
  hidden: false,
  value: 0,
  component: 'Slider',
  componentProps: {
    disabled: false,
    min: 0,
    max: 100,
    step: 1,
    showInput: false,
    showInputControls: true,
    showStops: false,
    showTooltip: true,
    range: false,
    vertical: false,
    height: null,
    debounce: 300
  },
  componentEvent: {},
  formItemProps: {
    noLabel: false,
    labelPosition: 'right',
    subLabel: '',
    autoRules: []
  },
  layoutProps: {
    span: 12,
    alone: false
  },
  insideProps: {},
  outsideProps: {
    enable: false,
    direction: 'row',
    style: {}
  }
}
```

## 可配置属性

**基本属性**
- `key` - 组件唯一标识符
- `field` - 字段名称，用于表单数据绑定
- `type` - 组件类型（固定为Inputer）
- `component` - 组件名称（固定为Slider）
- `label` - 字段标签文本
- `_d_label` - 动态标签配置（ResolverValue类型）
- `hidden` - 是否隐藏组件
- `_d_hidden` - 动态隐藏配置（ResolverValue类型）
- `value` - 默认数值（当表单初始化时，会自动为空的组件字段创建默认值）
- `_d_value` - 动态默认值配置（ResolverValue类型）

**组件属性 (componentProps)**
- `disabled` - 是否禁用
- `_d_disabled` - 动态禁用配置（ResolverValue类型）
- `min` - 最小值
- `max` - 最大值
- `step` - 步长
- `showInput` - 是否显示输入框，仅在非范围选择时有效
- `showInputControls` - 在显示输入框的情况下，是否显示输入框的控制按钮
- `showStops` - 是否显示断点
- `showTooltip` - 是否显示 tooltip
- `vertical` - 是否垂直模式
- `height` - 滑块高度，垂直模式时必填
- `debounce` - 输入时的防抖延迟，单位为毫秒，仅在 show-input 等于 true 时有效
- `style` - 自定义样式对象

**标题属性 (formItemProps)**
- `noLabel` - 是否不显示标签
- `labelPosition` - 标签位置（left、right、top）
- `labelWidth` - 标签宽度
- `labelMaxWidth` - 标签最大宽度
- `subLabel` - 副标签文本
- `autoRules` - 自动校验规则
- `_d_rules` - 动态校验规则配置（ResolverValue类型）

**布局属性 (layoutProps)**
- `span` - 栅格占据的列数（1-24）
- `alone` - 是否独占一行
- `colStyle` - 列自定义样式对象

**外部属性 (outsideProps)**
- `enable` - 是否启用外层包装
- `direction` - 包装方向（row、column）
- `style` - 自定义样式对象

**组件事件 (componentEvent)**
- `_d_onChange` - 值改变时触发的回调函数（ResolverValue类型）
  - 参数: `event`（组件新的值，数字或数字数组）, `formModel`, `column`, `disabled`, `excontext`
  - 返回值: 无需返回
