title: Alert组件
description: Alert提示组件的用途、默认参数和可配置项说明
keywords: Alert,提示组件,装饰型组件,组件配置
category: 组件菜单类
---
# Alert 提示组件

## 组件用途
Alert 是装饰型组件，用于在表单中显示提示信息。不参与表单数据收集，仅用于展示和装饰。
- **表单提示** - 在表单中显示重要提示信息
- **操作反馈** - 显示操作成功或失败的提示
- **注意事项** - 提醒用户注意某些重要信息

## 默认配置
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: '',
  type: 'Decorator',
  label: '新建提示',
  component: 'Alert',
  componentProps: {
    title: '提示',
    type: 'primary',
    description: '这是一条提示信息',
    closable: false,
    center: false,
    closeText: '',
    showIcon: true,
    effect: 'light',
    style: {}
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
- `component` - 组件名称（固定为Alert）
- `hidden` - 是否隐藏组件
- `_d_hidden` - 动态隐藏配置（ResolverValue类型）

**组件属性 (componentProps)**
- `title` - 提示标题文本
- `type` - 提示类型，可选值: primary、success、warning、error、info
- `description` - 提示描述文本
- `closable` - 是否显示关闭按钮
- `center` - 文字是否居中
- `closeText` - 关闭按钮文本
- `showIcon` - 是否显示图标
- `effect` - 主题样式，可选值: light、dark
- `style` - 自定义样式对象

**布局属性 (layoutProps)**
- `span` - 栅格占据的列数（1-24）
- `alone` - 是否独占一行

**外部属性 (outsideProps)**
- `enable` - 是否启用外层包装
- `direction` - 包装方向（row、column）
- `style` - 自定义样式对象

