title: FormSchemaBase数据结构
description: FormSchemaBase核心数据结构说明，定义AeForm高级表单组件的核心组件配置结构
keywords: FormSchemaBase,表单配置,组件配置,基础结构
category: 数据结构类

# FormSchemaBase数据结构

## 概述

FormSchemaBase是advanced-ele-ui中AeForm组件使用的核心数据结构，定义了表单组件的配置基础。DesignerFormSchema继承自FormSchemaBase并扩展了动态属性能力。

## 核心属性

### key

类型: string
说明: 组件的唯一标识符
默认值: 未设置时默认取field属性值
用途: 标识组件的唯一标志，非输入性组件必须设置

### field

类型: string
说明: 输入性组件的v-model绑定值
用途: 支持嵌套属性如userinfo.username
注意: 未设置key时，会默认使用此属性作为组件的key

### type

类型: FormSchemaType
可选值: 'Step' | 'Container' | 'Decorator' | 'Custom' | 'Inputer'
默认值: 'Inputer'
说明: 当前Schema的类型
Step: 步骤块，无FormItem包裹
Container: 容器块，无FormItem包裹
Decorator: 装饰性组件，无FormItem包裹
Custom: 自定义组件，有FormItem包裹
Inputer: 输入组件，有FormItem包裹

### label

类型: FormSchemaFn<string> | string
说明: 用于FormItem的标题或容器组件的标题
支持: 函数式、静态值、表达式三种形式
注意: 若希望不显示标题，建议通过formItemProps.noLabel属性控制

### hidden

类型: FormSchemaFn<boolean> | boolean
默认值: false
说明: 是否隐藏当前块或组件
支持: 函数式、静态值、表达式三种形式

### value

类型: FormSchemaFn<any> | any
默认值: null（非数组型组件）或Array([])（多选/表格组件）
说明: 输入组件的初始值
支持: 函数式、静态值、表达式三种形式
注意: 仅对Inputer或Custom类型的组件生效

## 嵌套属性结构

### componentProps

类型: ComponentProps
说明: 为组件添加属性
用途: 配置组件特有的属性，如Input的placeholder、Select的options等

### componentEvent

类型: ComponentEvent
说明: 为组件添加事件
用途: 配置组件的事件处理函数，如change、click等

### formItemProps

类型: FormItemProps
说明: 为组件添加表单属性
用途: 配置FormItem的属性，如noLabel、labelPosition、rules等

### layoutProps

类型: LayoutProps
说明: 布局属性，可设置组件外层的el-col的属性
用途: 配置组件的布局，如span、offset等

### outsideProps

类型: OutsideProps
说明: 为任何组件前置及后置添加自定义组件
用途: 在组件前后添加自定义内容

### insideProps

类型: InsideProps
说明: 为组件自身添加插槽内容
用途: 配置组件的插槽，如prefix、suffix等

## 特殊类型说明

### Step类型

必填属性: key、type、step、children
说明: 步骤块用于分步表单，根据FormProps.step属性过滤对应的步骤块
限制: 不支持嵌套Step类型

### Container类型

必填属性: key、type、component、children
说明: 容器块用于分组和布局，可包含子组件
组件: 使用ContainerName类型的组件，如Group等

### Decorator类型

必填属性: key、type、component
说明: 装饰性组件用于展示和装饰，不参与表单数据收集
组件: 使用DecoratorName类型的组件，如Alert、Text、Image等

### Inputer类型

必填属性: field、component
说明: 输入组件用于数据输入，有FormItem包裹
组件: 使用InputerName类型的组件，如Input、Select、DatePicker等

### Custom类型

必填属性: field、type、render
说明: 自定义组件通过render函数或Form下的slot渲染
用途: 实现自定义的组件渲染逻辑

## 函数类型说明

### FormSchemaFn

类型: (form: Recordable, column: FormSchema, disabled: boolean, excontext: Recordable) => T
说明: 表单Schema函数，用于动态计算属性值
参数: form表单数据、column当前配置、disabled是否禁用、excontext外部上下文
返回值: 属性值的类型T

### FormSchemaDomFn

类型: (excontext: Recordable) => VNode
说明: DOM渲染函数，用于返回VNode
参数: excontext外部上下文
返回值: Vue的VNode对象

## 使用示例

基础输入组件示例：
```
{
  field: 'name',
  component: 'Input',
  label: '姓名',
  value: '',
  componentProps: {
    placeholder: '请输入姓名'
  }
}
```

容器组件示例：
```
{
  key: 'group1',
  type: 'Container',
  component: 'Group',
  label: '基本信息',
  children: [
    { field: 'name', component: 'Input', label: '姓名' },
    { field: 'age', component: 'Input', label: '年龄' }
  ]
}
```

## 注意事项

FormSchemaBase是运行时使用的数据结构，DesignerFormSchema会被转换为FormSchemaBase
函数式属性在运行时执行，需要注意执行顺序和依赖关系
表达式属性通过eval执行，需注意安全性
某些属性仅对特定类型的组件生效，需注意类型限制
