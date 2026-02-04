title: Group组件
description: Group分组卡片组件的用途、默认参数和可配置项说明
keywords: Group,分组卡片,容器型组件,组件配置
category: 组件菜单类
---
# Group 分组卡片

## 组件用途
Group 是容器型组件，提供一种具有模块标题的分组容器，可将子组件容纳在其中，支持折叠展开。用于表单内容的逻辑分组和视觉分组。
- **表单分组** - 将表单内容按逻辑分组
- **折叠展开** - 通过折叠展开功能管理大量内容
- **视觉分组** - 通过卡片样式进行视觉分组

## 默认配置
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  type: 'Container',
  label: '新建卡片分组',
  hidden: false,
  component: 'Group',
  componentProps: {
    toggleable: true,
    expand: true,
    headerStyle: {},
    bodyStyle: {},
    labelStyle: {},
    subLabelStyle: {}
  },
  componentEvent: {},
  formItemProps: {
    subLabel: ''
  },
  layoutProps: {
    span: 24,
    alone: true
  },
  insideProps: {},
  children: []
}
```

## 可配置属性

**基本属性**
- `key` - 组件唯一标识符
- `type` - 组件类型（固定为Container）
- `component` - 组件名称（固定为Group）
- `label` - 分组标题
- `hidden` - 是否隐藏组件

**组件属性 (componentProps)**
- `headerStyle` - 标题栏样式对象（自定义分组标题样式）
- `bodyStyle` - 内容栏样式对象（自定义分组内容样式）
- `labelStyle` - 标题样式对象（自定义分组标签样式）
- `subLabelStyle` - 副标题样式对象（自定义分组副标题样式）

**标题属性 (formItemProps)**
- `subLabel` - 分组副标题

**布局属性 (layoutProps)**
- `span` - 栅格占据的列数（1-24）
- `alone` - 是否独占一行
- `colStyle` - 列自定义样式对象

**子组件配置**
- `children` - 子组件数组（DesignerFormSchema[]），用于容纳其他组件，支持多级嵌套
