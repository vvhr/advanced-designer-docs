title: DesignerFormSchema数据结构
description: DesignerFormSchema核心数据结构说明，定义表单设计器的配置结构
keywords: DesignerFormSchema,表单配置,组件配置,数据结构
category: 数据结构类
---

## 概述
DesignerFormSchema 是低代码表单设计器的标准化核心可序列化 JSON 配置载体，继承 AeForm 组件的 FormSchemaBase 类型，为其中无法直接 JSON 描述的属性添加_d_前缀标识并绑定 ResolverValue 结构；该结构支持以文本化 JS 代码表达式配置存储抽象属性值，且通过 resolver 属性区分方法函数的入参规则与运行机制，解决了表单组件普通与特殊属性的统一配置、存储及解析问题。

- DesignerFormSchema 会被转换为 FormSchemaBase 用于运行时渲染
- 特殊类型或需要动态返回的属性通过 `_d_` 前缀存储, 并通过 ResolverValue 结构赋值
- `__d_locked` 属性仅在设计器内部使用，不影响运行时
- 若 `_d_` 属性与普通属性名同时存在时, `_d_`属性将会覆盖普通属性, 比如 `_d_label` 将覆盖 `label`

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

## 特殊属性机制

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
- `FORM_SCHEMA_FN`: 任何需要动态化的属性值, 方法入参为: formModel, column, disabled, excontext
- `COMPONENT_EVENT_FN` - 专用于描述组件事件函数的解析器, 方法入参为: event, formModel, column, disabled, excontext
- `IMMEDIATE_EXECUTE` - 该属性并不需要在运行时动态取值时, 直接运行该方法(无参数), 获取返回值作为属性值.
- `FORM_SCHEMA_DOM_FN` - 基于特殊的JSON配置来返回DOM元素, 适用于render类型的属性.

## 嵌套属性详解

**componentProps** - 组件属性配置
- 包含组件特有的属性，如 Input 的 placeholder、Select 的 options 等
- 支持动态属性配置，如 _d_disabled, _d_style

**componentEvent** - 组件事件配置
- 键名为事件名，值为 ResolverValue 类型的事件处理函数配置
- 例如: _d_onChange、_d_onClick、_d_onBlur 等事件

**formItemProps** - 表单项属性配置
- 包含表单项的配置，如 noLabel、labelPosition、autoRules 等
- 支持动态属性配置, 如 _d_rules

**layoutProps** - 布局属性配置
- 包含组件的布局配置，如 span、alone 等

**outsideProps** - 外部属性配置
- 包含组件外层的包装配置，如 enable、direction、style 等
- 支持动态属性配置, 如 _d_prependRender, _d_appendRender

**insideProps.renders** - 组件内部插槽配置
- 根据 component 决定组件内部提供了哪些插槽

## 基础组件配置
```typescript
// 所有属性值都是静态值且无特殊类型时
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

## 特殊类型的属性配置
```typescript
// label属性需要动态化返回时, 新建_d_label属性.
const schema: DesignerFormSchema = {
  key: 'input1',
  field: 'name',
  type: 'Inputer',
  component: 'Input',
  label: '姓名',
  _d_label: {
    enable: true,
    value: '{{ excontext.userName || "姓名" }}',
    prop: 'label',
    resolver: 'FORM_SCHEMA_FN'
  }
}
```

## 容器组件配置
```typescript
// 容器组件必须是 Container, 并必须拥有 children 属性
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

