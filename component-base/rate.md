title: Rate组件
description: Rate评分按钮组件的用途、默认参数和可配置项说明
keywords: Rate,评分组件,输入型组件,组件配置
category: 组件菜单类
---
# Rate 评分

## 组件用途
Rate 是输入型组件，用于对事物进行评级操作。通过点击星星或其他图标进行评分。
- **产品评价** - 对产品进行评分
- **服务评价** - 对服务质量进行评分
- **满意度调查** - 在满意度调查表单中使用

## 默认配置
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: '',
  type: 'Inputer',
  label: '新建评分按钮',
  hidden: false,
  value: 0,
  component: 'Rate',
  componentProps: {
    disabled: false,
    max: 5,
    allowHalf: false,
    lowThreshold: 2,
    highThreshold: 4,
    showText: true,
    showScore: false,
    textColor: '#1f2937',
    texts: ['极差', '差', '一般', '好', '极好']
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
- `component` - 组件名称（固定为Rate）
- `label` - 字段标签文本
- `_d_label` - 动态标签配置（ResolverValue类型）
- `hidden` - 是否隐藏组件
- `_d_hidden` - 动态隐藏配置（ResolverValue类型）
- `value` - 默认值（数字类型，0-max之间）
- `_d_value` - 动态默认值配置（ResolverValue类型）

**组件属性 (componentProps)**
- `disabled` - 是否禁用
- `_d_disabled` - 动态禁用配置（ResolverValue类型）
- `max` - 最大分值（范围1-10）
- `allowHalf` - 是否允许半选
- `lowThreshold` - 低分阈值（低分和中等分数的界限值）
- `highThreshold` - 高分阈值（高分和中等分数的界限值）
- `showText` - 是否显示辅助文字
- `showScore` - 是否显示当前分数
- `textColor` - 辅助文字的颜色
- `texts` - 辅助文字数组
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
  - 参数: `event`（组件新的值，评分数字）, `formModel`, `column`, `disabled`, `excontext`
  - 返回值: 无需返回
