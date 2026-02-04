title: DesignerFormSchema数据结构
description: DesignerFormSchema核心数据结构说明，定义表单设计器的配置结构
keywords: DesignerFormSchema,表单配置,组件配置,数据结构
category: 数据结构类
---

## 概述

DesignerFormSchema是表单设计器的核心数据结构，定义了表单中每个组件的完整配置信息。它继承自FormSchemaBase，并扩展了动态属性配置能力。

## 类型定义

```typescript
interface DesignerFormSchema extends FormSchemaBase {
  // 基本属性
  key: string                    // 组件的唯一标识符
  field: string                  // 表单字段名，用于数据绑定
  type: 'Decorator' | 'Inputer' | 'Container' | 'Step' | 'Descriptions'  // 组件类型
  component: string              // 组件名称，如 Input、Select、Alert 等
  label: string                  // 组件标签文本
  hidden: boolean                // 是否隐藏组件
  value: any                     // 组件的默认值

  // 动态属性（_d_ 前缀）
  _d_hidden?: ResolverValue      // 动态隐藏配置
  _d_label?: ResolverValue       // 动态标签配置
  _d_value?: ResolverValue       // 动态值配置
  _d_disabled?: ResolverValue    // 动态禁用配置
  _d_rules?: ResolverValue       // 动态校验规则配置

  // 嵌套属性结构
  componentProps?: FormSchemaBase['componentProps'] & DesignerDynamicProps  // 组件属性配置
  componentEvent?: DesignerDynamicProps                                     // 组件事件配置
  formItemProps?: FormSchemaBase['formItemProps'] & DesignerDynamicProps    // 表单项属性配置
  layoutProps?: FormSchemaBase['layoutProps'] & DesignerDynamicProps        // 布局属性配置
  outsideProps?: FormSchemaBase['outsideProps'] & DesignerDynamicProps      // 外部属性配置
  insideProps?: {
    renders?: DesignerDynamicProps  // 插槽配置
  }

  // 子组件配置
  children?: DesignerFormSchema[]  // 子组件数组，用于容器型组件

  // 设计器内部属性
  __d_locked?: boolean            // 组件是否被锁定（锁定后不可编辑和删除）
}
```

## 动态属性机制

DesignerFormSchema支持通过 `_d_` 前缀实现动态属性配置。动态属性使用 ResolverValue 类型：

```typescript
interface ResolverValue {
  enable: boolean      // 是否启用动态属性，默认 false
  value: any          // 动态属性的值内容
  prop: string        // 实际字段名，默认从 _d_ 前缀后的字段名截取
  resolver: 'FORM_SCHEMA_FN' | 'COMPONENT_EVENT_FN' | 'IMMEDIATE_EXECUTE' | 'FORM_SCHEMA_DOM_FN'
}
```

**解析器类型说明:**
- `FORM_SCHEMA_FN` - 表单函数，接收 excontext 参数
- `COMPONENT_EVENT_FN` - 组件事件函数，接收事件参数
- `IMMEDIATE_EXECUTE` - 立即执行函数
- `FORM_SCHEMA_DOM_FN` - DOM渲染函数

## 嵌套属性详解

**componentProps** - 组件属性配置
- 包含组件特有的属性，如 Input 的 placeholder、Select 的 options 等
- 支持动态属性配置

**componentEvent** - 组件事件配置
- 键名为事件名，值为 ResolverValue 类型的事件处理函数配置
- 例如: change、click、blur 等事件

**formItemProps** - 表单项属性配置
- 包含表单项的配置，如 noLabel、labelPosition、autoRules 等
- 支持动态属性配置

**layoutProps** - 布局属性配置
- 包含组件的布局配置，如 span、alone 等
- 支持动态属性配置

**outsideProps** - 外部属性配置
- 包含组件外层的包装配置，如 enable、direction、style 等
- 支持动态属性配置

**insideProps** - 内部属性配置
- 包含 renders 等插槽配置
- renders 类型为 DesignerDynamicProps，用于配置组件的插槽内容

## 使用示例

**基础组件配置:**

```typescript
const schema: DesignerFormSchema = {
  key: 'input1',
  field: 'name',
  type: 'Inputer',
  component: 'Input',
  label: '姓名',
  hidden: false,
  value: '',
  componentProps: {
    placeholder: '请输入姓名',
    maxlength: 20
  }
}
```

**动态属性配置:**

```typescript
const schema: DesignerFormSchema = {
  key: 'input1',
  field: 'name',
  type: 'Inputer',
  component: 'Input',
  label: '姓名',
  _d_label: {
    enable: true,
    value: '(excontext) => excontext.userName || "姓名"',
    prop: 'label',
    resolver: 'FORM_SCHEMA_FN'
  }
}
```

**容器组件配置:**

```typescript
const schema: DesignerFormSchema = {
  key: 'group1',
  field: '',
  type: 'Container',
  component: 'Group',
  label: '基本信息',
  children: [
    {
      key: 'input1',
      field: 'name',
      type: 'Inputer',
      component: 'Input',
      label: '姓名'
    }
  ]
}
```

## 注意事项

- DesignerFormSchema 会被转换为 FormSchemaBase 用于运行时渲染
- 动态属性通过 schema-resolver 工具函数进行解析和转换
- 配置错误可能导致组件无法正常渲染，需注意数据结构的正确性
- `__d_locked` 属性仅在设计器内部使用，不影响运行时
