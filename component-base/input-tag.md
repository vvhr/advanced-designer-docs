title: InputTag组件
description: InputTag标签输入框组件的用途、默认参数和可配置项说明
keywords: InputTag,标签输入框,输入型组件,组件配置
category: 组件菜单类
---
# InputTag 标签输入框

## 组件用途
InputTag 是输入型组件，通过输入内容创建标签。支持多个标签的输入和管理。
- **标签输入** - 输入多个标签，如技能标签、兴趣标签等
- **关键词输入** - 输入多个关键词
- **分类选择** - 通过标签进行分类

## 默认配置
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: '',
  type: 'Inputer',
  label: '新建标签输入框',
  hidden: false,
  value: [],
  component: 'InputTag',
  componentProps: {
    disabled: false,
    clearable: false,
    max: null,
    tagType: 'info',
    trigger: 'Enter',
    draggable: false,
    delimiter: null,
    collapseTags: false
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
- `component` - 组件名称（固定为InputTag）
- `label` - 字段标签文本
- `_d_label` - 动态标签配置（ResolverValue类型）
- `hidden` - 是否隐藏组件
- `_d_hidden` - 动态隐藏配置（ResolverValue类型）
- `value` - 默认值（数组类型，存储标签数组）
- `_d_value` - 动态默认值配置（ResolverValue类型）

**组件属性 (componentProps)**
- `disabled` - 是否禁用
- `_d_disabled` - 动态禁用配置（ResolverValue类型）
- `clearable` - 是否显示清除按钮
- `placeholder` - 占位文本
- `max` - 最大标签数（最大可输入的标签数量）
- `tagType` - 标签类型，可选值: info（信息）、success（成功）、warning（警告）、error（错误）
- `trigger` - 触发键，可选值: Enter（回车）、Space（空格）
- `draggable` - 标签是否可拖拽排序
- `delimiter` - 分隔符（当匹配到分隔符时，自动添加标签）
- `collapseTags` - 当标签过多时，是否将标签折叠为文字
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
  - 参数: `event`（组件新的值）, `formModel`, `column`, `disabled`, `excontext`
  - 返回值: 无需返回
- `_d_onClear` - 点击清除按钮时触发的回调函数（ResolverValue类型）
  - 参数: `event`, `formModel`, `column`, `disabled`, `excontext`
  - 返回值: 无需返回
