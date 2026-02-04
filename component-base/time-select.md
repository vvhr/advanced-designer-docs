title: TimeSelect组件
description: TimeSelect时刻下拉选择框组件的用途、默认参数和可配置项说明
keywords: TimeSelect,时间选择,输入型组件,组件配置
category: 组件菜单类
---
# TimeSelect 时刻下拉选择器

## 组件用途
TimeSelect 是输入型组件，用于从下拉列表中选择时刻。通过固定时间间隔的下拉列表选择时刻。
- **时刻选择** - 从固定时间间隔中选择时刻
- **预约时间** - 选择预约时间段
- **时间设置** - 设置固定间隔的时间

## 默认配置
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: '',
  type: 'Inputer',
  label: '新建时刻下拉选择框',
  hidden: false,
  value: null,
  component: 'TimeSelect',
  componentProps: {
    disabled: false,
    clearable: false,
    placeholder: null,
    start: '09:00',
    end: '18:00',
    step: '00:30',
    minTime: null,
    maxTime: null,
    format: 'HH:mm',
    valueFormat: 'HH:mm'
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
- `component` - 组件名称（固定为TimeSelect）
- `label` - 字段标签文本
- `_d_label` - 动态标签配置（ResolverValue类型）
- `hidden` - 是否隐藏组件
- `_d_hidden` - 动态隐藏配置（ResolverValue类型）
- `value` - 默认值
- `_d_value` - 动态默认值配置（ResolverValue类型）

**组件属性 (componentProps)**
- `disabled` - 是否禁用
- `_d_disabled` - 动态禁用配置（ResolverValue类型）
- `clearable` - 是否显示清除按钮
- `placeholder` - 占位文本
- `start` - 开始时间
- `end` - 结束时间
- `step` - 时间间隔
- `minTime` - 最小时间
- `maxTime` - 最大时间
- `format` - 显示格式
- `valueFormat` - 取值格式
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
