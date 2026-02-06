title: ResolverValue数据结构
description: ResolverValue核心数据结构说明，定义表单设计器的抽象函数可视化配置引擎的数据结构
keywords: ResolverValue,动态属性,解析器,函数配置
category: 数据结构类
---

## ResolverValue 概述
ResolverValue是表单设计器中用于实现特殊或动态属性文本化配置的核心数据结构。
它通过抽象函数可视化配置引擎，将函数代码转换为可配置的动态属性。
- ResolverValue的`value`字段存储的是函数代码字符串
- 函数代码会在运行时通过`new Function`执行，需注意安全性
- `prop`字段用于指定实际字段名，如果不指定则从`_d_`前缀后截取
- `enable`字段控制是否启用该属性，`false`时则不会被解析.
- 不同的`resolver`类型对应不同的函数签名和编辑器

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

## FORM_SCHEMA_FN - 表单Schema函数
```typescript
// 函数签名
export type FormSchemaFn<T> = (
  form: Recordable,
  column: FormSchema,
  disabled: boolean,
  excontext: Recordable
) => T
// 使用场景
// - _d_label: 动态标签
// - _d_hidden: 动态隐藏
// - _d_disabled: 动态禁用
// - _d_value: 动态值
```
**动态标签配置示例:**
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


## COMPONENT_EVENT_FN - 组件事件函数
```typescript
/**
 * 自定义组件原生事件
 * @description 当事件触发时，需要执行一些逻辑，则可以使用此属性。
 * @param event - 原始事件参数
 * @param form - 表单数据对象
 * @param column - 当前列配置
 * @param disabled - 表单自身是否禁用
 * @param excontext - 表单数据源上下文
 */
export type ComponentEventFn<T extends any> = (
  event: T,
  form: Recordable,
  column: FormSchema,
  disabled: boolean,
  excontext: Recordable
) => void

// 使用场景
// - componentEvent._d_onChange: 值改变事件
// - componentEvent._d_onClick: 点击事件
// - componentEvent._d_onBlur: 失焦事件
// - componentEvent._d_onFocus: 聚焦事件
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
    _d_onChange: resolverValue  // change事件处理
  }
}
```

## IMMEDIATE_EXECUTE - 立即取值函数
```typescript
// 函数签名
type ImmediateExecuteFn = () => any

// 使用场景
// - formItems._d_rules
```
**文本化配置rules示例**
```typescript
const resolverValue: ResolverValue = {
  enable: false,
  prop: 'rules',
  value: '{{ return [{ required: true, message: "必填项不得为空", trigger: "change" }]; }}',
  resolver: 'IMMEDIATE_EXECUTE'
}
// 在DesignerFormSchema中使用
const schema = {
  field: 'email',
  component: 'Input',
  label: '邮箱',
  formItemProps: {
    _d_rules: resolverValue
  }
}
```


## FORM_SCHEMA_DOM_FN - DOM渲染函数
```typescript
// 函数签名
/**
 * 动态取VNode函数
 * @description 基于某种逻辑动态取值
 * @param form - 表单数据对象
 * @param column - 当前列配置
 * @param disabled - 表单自身是否禁用
 * @param excontext - 表单数据源上下文
 * @param slotProps - 插槽自身携带的参数（作用域插槽参数）
 */
export type FormSchemaDomFn<T> = (
  form: Recordable,
  column: FormSchema,
  disabled: boolean,
  excontext: Recordable,
  ...slotProps: any[]
) => T

// 使用场景
// - outsideProps._d_prependRender
// - outsideProps._d_appendRender
```

**为Table组件在前面添加一个按钮组件:**
```typescript
const resolverValue: ResolverValue = {
  enable: true,
  prop: 'prependRender',
  value: {
    type: 'el-button',
    props: { type: 'primary' },
    children: '添加',
    events: { click: 'console.log("点击了添加按钮")' }
  },
  resolver: 'FORM_SCHEMA_DOM_FN'
}

// 在DesignerFormSchema中使用
const schema = {
  field: 'table',
  component: 'Table',
  label: '列表',
  outsideProps: {
    enable: true,
    _d_prependRender: resolverValue
  }
}
```
