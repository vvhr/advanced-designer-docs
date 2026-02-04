title: InputNumber组件
description: InputNumber数值输入框组件的用途、默认参数和可配置项说明
keywords: InputNumber,数值输入框,输入型组件,组件配置
category: 组件菜单类
---
# InputNumber 数值输入框

## 组件用途
InputNumber 是输入型组件，仅允许输入标准的数字值，可定义范围。用于输入数字类型的表单字段。
- **数字输入** - 输入年龄、数量、金额等数字
- **范围限制** - 通过min和max限制输入范围
- **精度控制** - 通过precision控制小数位数

## 默认配置
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: '',
  type: 'Inputer',
  label: '新建数值输入框',
  hidden: false,
  value: null,
  component: 'InputNumber',
  componentProps: {
    disabled: false,
    min: null,
    max: null,
    step: 1,
    stepStrictly: false,
    precision: null,
    controls: false,
    controlsPosition: '',
    placeholder: null,
    validateEvent: true,
    align: 'left',
    style: { width: '100%' }
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
- `component` - 组件名称（固定为InputNumber）
- `label` - 字段标签文本
- `_d_label` - 动态标签配置（ResolverValue类型）
- `hidden` - 是否隐藏组件
- `_d_hidden` - 动态隐藏配置（ResolverValue类型）
- `value` - 默认数值（当表单初始化时，会自动为空的组件字段创建默认值）
- `_d_value` - 动态默认值配置（ResolverValue类型）

**组件属性 (componentProps)**
- `disabled` - 是否禁用
- `_d_disabled` - 动态禁用配置（ResolverValue类型）
- `placeholder` - 占位文本
- `min` - 最小值（设置计数器允许的最小值）
- `max` - 最大值（设置计数器允许的最大值）
- `step` - 步长（计数器步长）
- `stepStrictly` - 是否只能输入步长的倍数
- `precision` - 精度（数值精度，即小数位数，范围0-20）
- `controls` - 是否使用控制按钮
- `controlsPosition` - 控制按钮位置，可选值: ''（默认）、right（右侧）
- `align` - 内容对齐，可选值: left（居左）、center（居中）、right（居右）
- `validateEvent` - 输入时是否触发表单验证
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
- `_d_onBlur` - 失去焦点时触发的回调函数（ResolverValue类型）
  - 参数: `event`, `formModel`, `column`, `disabled`, `excontext`
  - 返回值: 无需返回
- `_d_onFocus` - 获得焦点时触发的回调函数（ResolverValue类型）
  - 参数: `event`, `formModel`, `column`, `disabled`, `excontext`
  - 返回值: 无需返回
- `_d_onChange` - 值改变时触发的回调函数（ResolverValue类型）
  - 参数: `event`（组件新的值，数字）, `formModel`, `column`, `disabled`, `excontext`
  - 返回值: 无需返回
