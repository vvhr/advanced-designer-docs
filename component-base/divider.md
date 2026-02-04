title: Divider组件
description: Divider分隔线组件的用途、默认参数和可配置项说明
keywords: Divider,分隔线,装饰型组件,组件配置
category: 组件菜单类
---
# Divider 分隔线组件

## 组件用途
Divider是装饰型组件，用于在表单中显示分隔线。用于分隔内容区域，提升表单的可读性。不参与表单数据收集，仅用于展示和装饰。

- **内容分隔** - 分隔表单中的不同内容区域
- **视觉分组** - 通过分隔线进行视觉分组
- **表单美化** - 提升表单的可读性和美观度

## 默认配置

```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: '',
  type: 'Decorator',
  label: '新建分隔线',
  component: 'Divider',
  componentProps: {
    direction: 'horizontal',
    borderStyle: 'solid',
    contentPosition: 'center'
  },
  componentEvent: {},
  formItemProps: {},
  layoutProps: {
    span: 12,
    alone: false
  },
  outsideProps: {},
  insideProps: {
    renders: {
      _d_default: {
        enable: false,
        prop: 'default',
        value: {
          type: 'span',
          children: '我是一条分隔线'
        },
        resolver: 'FORM_SCHEMA_DOM_FN'
      }
    }
  }
}
```

## 可配置属性

**基本属性**
- `key` - 组件唯一标识符
- `type` - 组件类型（固定为Decorator）
- `component` - 组件名称（固定为Divider）
- `hidden` - 是否隐藏组件
- `_d_hidden` - 动态隐藏配置（ResolverValue类型）

**组件属性 (componentProps)**
- `direction` - 分隔线方向，可选值: horizontal（水平）、vertical（垂直）
- `borderStyle` - 边框样式，可选值: solid（实线）、dashed（虚线）
- `contentPosition` - 内容位置，可选值: center（居中）、left（居左）、right（居右）
- `style` - 自定义样式对象

**内部属性 (insideProps)**
- `renders._d_default` - 分隔线默认内容插槽（ResolverValue类型）
  - 用于配置分隔线中间显示的内容

**布局属性 (layoutProps)**
- `span` - 栅格占据的列数（1-24）
- `alone` - 是否独占一行
- `colStyle` - 列自定义样式对象

**外部属性 (outsideProps)**
- `enable` - 是否启用外层包装
- `direction` - 包装方向（row、column）
- `style` - 自定义样式对象

