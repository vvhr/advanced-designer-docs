title: RadioButton组件
description: RadioButton单选按钮组组件的用途、默认参数和可配置项说明
keywords: RadioButton,单选按钮,输入型组件,组件配置
category: 组件菜单类
---
# RadioButton 单选按钮

## 组件用途
RadioButton 是输入型组件，用于单选场景。通过单选按钮组的形式展示选项，支持从多个选项中选择一个值。
- **单选场景** - 从多个选项中选择一个值
- **性别选择** - 选择性别等单选场景
- **状态选择** - 选择状态、类型等

## 默认配置
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: '',
  type: 'Inputer',
  label: '新单选按钮',
  hidden: false,
  value: '',
  component: 'RadioButton',
  componentProps: {
    disabled: false,
    clearable: false,
    options: [
      { value: '1', label: '选项1', disabled: false },
      { value: '2', label: '选项2', disabled: false }
    ],
    optionKeys: {
      label: 'label',
      value: 'value',
      children: 'children',
      disabled: 'disabled'
    },
    style: {}
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
- `component` - 组件名称（固定为RadioButton）
- `label` - 字段标签文本
- `_d_label` - 动态标签配置（ResolverValue类型）
- `hidden` - 是否隐藏组件
- `_d_hidden` - 动态隐藏配置（ResolverValue类型）
- `value` - 默认值（选中项的value值）
- `_d_value` - 动态默认值配置（ResolverValue类型）

**组件属性 (componentProps)**
- `disabled` - 是否禁用
- `_d_disabled` - 动态禁用配置（ResolverValue类型）
- `options` - 选项数组，每个选项包含value、label、disabled属性
- `_d_options` - 动态选项配置（函数编程动态返回选项列表，ResolverValue类型）
- `validateEvent` - 输入时是否触发表单验证
- `style` - 自定义样式对象
- `textColor` - 被选中项的按钮文本颜色
- `fill` - 被选中项的按钮填充色和边框色

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
  - 参数: `event`（组件新的值）, `formModel`, `column`, `disabled`, `excontext`
  - 返回值: 无需返回
