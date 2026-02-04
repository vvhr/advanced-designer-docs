title: Text组件
description: Text静态文本组件的用途、默认参数和可配置项说明
keywords: Text,静态文本,装饰型组件,组件配置
category: 组件菜单类
---
# Text 静态文本

## 组件用途
Text 是装饰型组件，用于在表单中显示静态文本内容。支持高亮、图标、截断、复制等功能。不参与表单数据收集，仅用于展示和装饰。
- **文本展示** - 显示说明文字、提示信息
- **高亮显示** - 高亮显示关键内容
- **可复制文本** - 提供文本复制功能

## 默认配置
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: '',
  type: 'Decorator',
  label: '新建提示',
  component: 'Text',
  componentProps: {
    value: '这是您应该配置的文本内容，您可以配置高亮、图标、样式等。',
    icon: '',
    iconStyle: {},
    dotType: '',
    block: false,
    patterns: ['高亮', '图标', '样式'],
    hlStyle: {},
    truncate: false,
    expandable: false,
    expandText: '展开',
    collapseText: '收起',
    copyable: false,
    copyIcon: 'ep:document-copy',
    copySuccessText: '复制成功'
  },
  componentEvent: {},
  formItemProps: {},
  layoutProps: {
    span: 12,
    alone: false
  },
  insideProps: {},
  outsideProps: {}
}
```

## 可配置属性

**基本属性**
- `key` - 组件唯一标识符
- `type` - 组件类型（固定为Decorator）
- `component` - 组件名称（固定为Text）
- `hidden` - 是否隐藏组件
- `_d_hidden` - 动态隐藏配置（ResolverValue类型）

**组件属性 (componentProps)**
- `value` - 内容（显示的文本内容）
- `icon` - 前置图标
- `iconStyle` - 前置图标样式
- `dotType` - 圆点类型，可选值: ''（无）、primary（主题色）、success（成功色）、warning（警告色）、error（错误色）、info（信息色）
- `block` - 是否显示为引用块
- `patterns` - 高亮内容（需要高亮的文本数组）
- `hlStyle` - 高亮样式
- `truncate` - 截断，可选值: false（禁止）、1（超出1行）、2（超出2行）、3（超出3行）
- `expandable` - 是否允许折叠
- `expandText` - 展开按钮文本
- `collapseText` - 折叠按钮文本
- `copyable` - 是否可复制
- `copyIcon` - 复制图标
- `copySuccessText` - 复制成功提示文本
- `style` - 自定义样式对象

**布局属性 (layoutProps)**
- `span` - 栅格占据的列数（1-24）
- `alone` - 是否独占一行
- `colStyle` - 列自定义样式对象

**外部属性 (outsideProps)**
- `enable` - 是否启用外层包装
- `direction` - 包装方向（row、column）
- `style` - 自定义样式对象
