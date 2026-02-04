title: Switch组件
description: Switch开关组件的用途、默认参数和可配置项说明
keywords: Switch,开关,输入型组件,组件配置
category: 组件菜单类
---
# Switch 开关

## 组件用途
Switch 是输入型组件，表示两种相互对立的状态间的切换，多用于触发「开/关」。
- **开关切换** - 表示开启或关闭状态
- **功能启用** - 启用或禁用某个功能
- **状态切换** - 在两种状态之间切换

## 默认配置
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: '',
  type: 'Inputer',
  label: '新建开关按钮',
  hidden: false,
  value: false,
  component: 'Switch',
  componentProps: {
    disabled: false,
    activeValue: true,
    inactiveValue: false,
    activeText: '',
    inactiveText: '',
    inlinePrompt: false,
    width: 40,
    validateEvent: true
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
- `component` - 组件名称（固定为Switch）
- `label` - 字段标签文本
- `_d_label` - 动态标签配置（ResolverValue类型）
- `hidden` - 是否隐藏组件
- `_d_hidden` - 动态隐藏配置（ResolverValue类型）
- `value` - 默认值（布尔类型或自定义值）
- `_d_value` - 动态默认值配置（ResolverValue类型）

**组件属性 (componentProps)**
- `disabled` - 是否禁用
- `_d_disabled` - 动态禁用配置（ResolverValue类型）
- `activeValue` - 开关打开时的值
- `inactiveValue` - 开关关闭时的值
- `activeText` - 开关打开时的文字描述
- `inactiveText` - 开关关闭时的文字描述
- `inlinePrompt` - 是否在开关内部显示文字
- `width` - 开关的宽度（像素）
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
- `_d_onChange` - 值改变时触发的回调函数（ResolverValue类型）
  - 参数: `event`（组件新的值）, `formModel`, `column`, `disabled`, `excontext`
  - 返回值: 无需返回
