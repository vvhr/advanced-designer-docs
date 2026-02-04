title: ResolverValue数据结构
description: ResolverValue核心数据结构说明，定义表单设计器的抽象函数可视化配置引擎的数据结构
keywords: ResolverValue,动态属性,解析器,函数配置
category: 数据结构类
---

## 概述

ResolverValue是表单设计器中用于实现动态属性配置的核心数据结构。它通过抽象函数可视化配置引擎，将函数代码转换为可配置的动态属性。

## 类型定义

```typescript
interface ResolverValue {
  enable: boolean           // 是否启用动态属性，默认false
  value: any               // 动态属性的值内容，通常为函数代码字符串
  prop: string             // 实际字段名，默认从_d_前缀后的字段名截取
  resolver: DesignResolver // 解析方法类型
}

// 解析器类型枚举
type DesignResolver =
  | 'FORM_SCHEMA_FN'        // 表单Schema函数
  | 'COMPONENT_EVENT_FN'    // 组件事件函数
  | 'IMMEDIATE_EXECUTE'     // 立即执行函数
  | 'FORM_SCHEMA_DOM_FN'    // DOM渲染函数
```

## 解析器类型详解

### FORM_SCHEMA_FN - 表单Schema函数

```typescript
// 函数签名
type FormSchemaFn = (excontext: Recordable) => any

// 使用场景
// - _d_label: 动态标签
// - _d_hidden: 动态隐藏
// - _d_disabled: 动态禁用
// - _d_value: 动态值
// - _d_rules: 动态校验规则

// 编辑器: FnEditor
```

### COMPONENT_EVENT_FN - 组件事件函数

```typescript
// 函数签名
type ComponentEventFn = (event: ComponentEvent, excontext: Recordable) => void

// 使用场景
// - componentEvent._d_onChange: 值改变事件
// - componentEvent._d_onClick: 点击事件
// - componentEvent._d_onBlur: 失焦事件
// - componentEvent._d_onFocus: 聚焦事件

// 编辑器: FnEditor
```

### IMMEDIATE_EXECUTE - 立即执行函数

```typescript
// 函数签名
type ImmediateExecuteFn = () => any

// 使用场景
// - formItems._d_rules

// 编辑器: FnEditor（自由编写）
```

### FORM_SCHEMA_DOM_FN - DOM渲染函数

```typescript
// 函数签名
type FormSchemaDomFn = (excontext: Recordable) => VNode

// 使用场景
// - outsideProps._d_prependRender
// - outsideProps._d_appendRender

// 编辑器: RenderDesigner（可视化VNode设计器）
```

## 使用示例

**动态标签配置:**

```typescript
const resolverValue: ResolverValue = {
  enable: true,
  value: '{{ excontext.userName || "姓名" }}',
  prop: 'label',
  resolver: 'FORM_SCHEMA_FN'
}

// 在DesignerFormSchema中使用
const schema = {
  field: 'name',
  component: 'Input',
  label: '姓名',
  _d_label: resolverValue  // 动态标签
}
```

**动态隐藏配置:**

```typescript
const resolverValue: ResolverValue = {
  enable: true,
  value: '{{ excontext.userRole === "admin" }}',
  prop: 'hidden',
  resolver: 'FORM_SCHEMA_FN'
}

// 在DesignerFormSchema中使用
const schema = {
  field: 'secretField',
  component: 'Input',
  label: '机密字段',
  _d_hidden: resolverValue  // 仅管理员可见
}
```

**事件处理函数配置:**

```typescript
const resolverValue: ResolverValue = {
  enable: true,
  value: '{{ console.log(event); excontext.handleChange(event); }}',
  prop: 'change',
  resolver: 'COMPONENT_EVENT_FN'
}

// 在DesignerFormSchema中使用
const schema = {
  field: 'email',
  component: 'Input',
  label: '邮箱',
  componentEvent: {
    change: resolverValue  // change事件处理
  }
}
```

**插槽渲染函数配置:**

```typescript
const resolverValue: ResolverValue = {
  enable: true,
  value: '{{ h("span", { class: "prefix-icon" }, "📧") }}',
  prop: 'prefix',
  resolver: 'FORM_SCHEMA_DOM_FN'
}

// 在DesignerFormSchema中使用
const schema = {
  field: 'email',
  component: 'Input',
  label: '邮箱',
  insideProps: {
    renders: {
      prefix: resolverValue  // 前缀插槽
    }
  }
}
```

## 解析流程

```typescript
// 1. 设计器配置阶段
// 用户通过可视化编辑器配置ResolverValue
const designerSchema = {
  field: 'name',
  _d_label: {
    enable: true,
    value: '{{ excontext.title }}',
    prop: 'label',
    resolver: 'FORM_SCHEMA_FN'
  }
}

// 2. Schema解析阶段
// schema-resolver工具函数将ResolverValue转换为实际的函数
const runtimeSchema = {
  field: 'name',
  label: (formModel, column, disabled, excontext) => excontext.title  // 转换为函数
}

// 3. 运行时执行
// 在表单渲染时执行函数，获取动态值
const labelValue = runtimeSchema.label({ title: '用户姓名' })  // '用户姓名'
```

## 注意事项

- ResolverValue的`value`字段存储的是函数代码字符串
- 函数代码会在运行时通过`new Function`或`eval`执行，需注意安全性
- `prop`字段用于指定实际字段名，如果不指定则从`_d_`前缀后截取
- `enable`字段控制是否启用动态属性，`false`时使用静态值
- 不同的`resolver`类型对应不同的函数签名和编辑器
