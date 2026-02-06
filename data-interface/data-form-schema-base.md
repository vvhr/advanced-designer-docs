title: FormSchemaBase数据结构
description: FormSchemaBase核心数据结构说明，定义AeForm高级表单组件的核心组件配置结构
keywords: FormSchemaBase,表单配置,组件配置,基础结构
category: 数据结构类
---

## 概述
FormSchemaBase是advanced-ele-ui组件库中AeForm组件使用的核心数据结构，定义了表单组件的配置基础。
在表单设计器项目中，DesignerFormSchema继承自FormSchemaBase并扩展了文本化存储特殊属性能力。

- FormSchemaBase是运行时使用的数据结构，在表单设计器项目中DesignerFormSchema会被转换为FormSchemaBase
- 函数式属性在运行时执行，需要注意执行顺序和依赖关系
- 表达式属性通过new Function构建并执行，需注意安全性
- 某些属性仅对特定类型的组件生效，需注意类型限制
- `key`属性未设置时会默认使用`field`值，非输入性组件必须设置`key`


## 类型定义

```typescript
interface FormSchemaBase {
  // 核心属性
  key?: string                                    // 组件的唯一标识符，未设置时默认取field值
  field: string                                   // 输入性组件的v-model绑定值，支持嵌套如userinfo.username
  type?: FormSchemaType                           // Schema类型，默认'Inputer'
  component?: string                              // 组件名称，如Input、Select等
  label?: FormSchemaFn<string> | string          // FormItem标题或容器标题
  hidden?: FormSchemaFn<boolean> | boolean       // 是否隐藏当前块或组件，默认false
  value?: FormSchemaFn<any> | any                // 输入组件的初始值

  // 嵌套属性结构
  componentProps?: ComponentProps                 // 组件属性配置
  componentEvent?: ComponentEvent                 // 组件事件配置
  formItemProps?: FormItemProps                   // 表单项属性配置
  layoutProps?: LayoutProps                       // 布局属性配置
  outsideProps?: OutsideProps                     // 外部包装配置
  insideProps?: InsideProps                       // 插槽内容配置

  // 容器组件专用
  children?: FormSchemaBase[]                     // 子组件数组
}

// Schema类型枚举
type FormSchemaType =
  | 'Step'        // 步骤块，无FormItem包裹
  | 'Container'   // 容器块，无FormItem包裹
  | 'Decorator'   // 装饰性组件，无FormItem包裹
  | 'Custom'      // 自定义组件，有FormItem包裹
  | 'Inputer'     // 输入组件，有FormItem包裹（默认）
```

## 函数类型定义

```typescript
/**
 * 动态取值函数
 * @description 基于某种逻辑动态取值
 * @param form - 表单数据对象
 * @param column - 当前列配置
 * @param disabled - 表单自身是否禁用
 * @param excontext - 表单数据源上下文
 */
export type FormSchemaFn<T> = (
  form: Recordable,
  column: FormSchema,
  disabled: boolean,
  excontext: Recordable
) => T

// DOM渲染函数
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
```

## 类型详解

**Step类型** - 步骤块
- 必填属性: `key`、`type`、`step`、`children`
- 用途: 分步表单，根据FormProps.step属性过滤对应的步骤块
- 限制: 不支持嵌套Step类型

**Container类型** - 容器块
- 必填属性: `key`、`type`、`component`、`children`
- 用途: 分组和布局，可包含子组件
- 组件: 使用ContainerName类型的组件，如Group等

**Decorator类型** - 装饰性组件
- 必填属性: `key`、`type`、`component`
- 用途: 展示和装饰，不参与表单数据收集
- 组件: 使用DecoratorName类型的组件，如Alert、Text、Image等

**Inputer类型** - 输入组件
- 必填属性: `field`、`component`
- 用途: 数据输入，有FormItem包裹
- 组件: 使用InputerName类型的组件，如Input、Select、DatePicker等

**Custom类型** - 自定义组件
- 必填属性: `field`、`type`、`render`
- 用途: 通过render函数或Form下的slot渲染
- 场景: 实现自定义的组件渲染逻辑

## 嵌套属性说明

**componentProps** - 组件属性配置
- 配置组件特有的属性，如Input的placeholder、Select的options等

**componentEvent** - 组件事件配置
- 配置组件的事件处理函数，如change、click等

**formItemProps** - 表单项属性配置
- 配置FormItem的属性，如noLabel、labelPosition、rules等

**layoutProps** - 布局属性配置
- 配置组件外层el-col的属性，如span、offset等

**outsideProps** - 外部包装配置
- 在组件前后添加自定义内容

**insideProps** - 插槽内容配置
- 配置组件的插槽，如prefix、suffix等

## 使用示例

**基础输入组件:**

```typescript
const schema: FormSchemaBase = {
  field: 'name',
  component: 'Input',
  label: '姓名',
  value: '',
  componentProps: {
    placeholder: '请输入姓名'
  }
}
```

**容器组件:**

```typescript
const schema: FormSchemaBase = {
  key: 'group1',
  type: 'Container',
  component: 'Group',
  label: '基本信息',
  children: [
    { field: 'name', component: 'Input', label: '姓名' },
    { field: 'age', component: 'InputNumber', label: '年龄' }
  ]
}
```

**函数式属性:**

```typescript
const schema: FormSchemaBase = {
  field: 'email',
  component: 'Input',
  label: (form, column, disabled, excontext) => {
    return excontext.isRequired ? '邮箱*' : '邮箱'
  },
  hidden: (form, column, disabled, excontext) => {
    return form.userType !== 'admin'
  }
}
```
