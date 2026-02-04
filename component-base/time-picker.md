title: TimePicker组件
description: TimePicker时刻面板选择框组件的用途、默认参数和可配置项说明
keywords: TimePicker,时间选择器,输入型组件,组件配置
category: 组件菜单类
---
# TimePicker 时刻面板选择器

## 组件用途
TimePicker 是输入型组件，用于选择时刻或时刻范围。通过面板选择时分秒。
- **时刻选择** - 选择具体的时刻
- **时刻范围** - 选择时刻范围
- **时间设置** - 设置开始和结束时间

## 默认配置
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: '',
  type: 'Inputer',
  label: '新建时刻面板选择框',
  hidden: false,
  value: null,
  component: 'TimePicker',
  componentProps: {
    disabled: false,
    editable: true,
    clearable: false,
    placeholder: null,
    startPlaceholder: '开始时间',
    endPlaceholder: '结束时间',
    isRange: false,
    arrowControl: false,
    format: 'HH:mm:ss',
    valueFormat: 'HH:mm:ss',
    rangeSeparator: '-'
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
- `component` - 组件名称（固定为TimePicker）
- `label` - 字段标签文本
- `_d_label` - 动态标签配置（ResolverValue类型）
- `hidden` - 是否隐藏组件
- `_d_hidden` - 动态隐藏配置（ResolverValue类型）
- `value` - 默认值
- `_d_value` - 动态默认值配置（ResolverValue类型）

**组件属性 (componentProps)**
- `disabled` - 是否禁用
- `_d_disabled` - 动态禁用配置（ResolverValue类型）
- `editable` - 文本框是否可输入
- `clearable` - 是否显示清除按钮
- `placeholder` - 占位文本
- `startPlaceholder` - 开始时间占位文本
- `endPlaceholder` - 结束时间占位文本
- `isRange` - 是否为时间范围选择
- `arrowControl` - 是否使用箭头进行时间选择
- `format` - 显示格式
- `valueFormat` - 取值格式
- `rangeSeparator` - 范围分隔符
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
- `_d_onBlur` - 失去焦点时触发的回调函数（ResolverValue类型）
- `_d_onFocus` - 获得焦点时触发的回调函数（ResolverValue类型）
