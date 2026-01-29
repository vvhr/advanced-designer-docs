title: DesignerFormSchema数据结构
description: DesignerFormSchema核心数据结构说明，定义表单设计器的配置结构
keywords: DesignerFormSchema,表单配置,组件配置,数据结构
category: 数据结构类

# DesignerFormSchema数据结构

## 概述

DesignerFormSchema是表单设计器的核心数据结构，定义了表单中每个组件的完整配置信息。它继承自FormSchemaBase，并扩展了动态属性配置能力。

## 基本结构

DesignerFormSchema包含以下主要属性：

key: 组件的唯一标识符，字符串类型
field: 表单字段名，用于数据绑定，字符串类型
type: 组件类型，可选值包括Decorator、Inputer、Container、Step、Descriptions
component: 组件名称，对应advanced-ele-ui中的组件名，如Input、Select、Alert等
label: 组件标签文本，字符串类型
hidden: 是否隐藏组件，布尔类型
value: 组件的默认值，任意类型

## 动态属性机制

DesignerFormSchema支持通过_d_前缀实现动态属性配置。动态属性使用ResolverValue类型，包含以下字段：

enable: 是否启用动态属性，默认false
value: 动态属性的值内容，任意类型
prop: 实际字段名，默认从_d_前缀后的字段名截取
resolver: 解析方法类型，可选值包括FORM_SCHEMA_FN、COMPONENT_EVENT_FN、IMMEDIATE_EXECUTE、FORM_SCHEMA_DOM_FN

## 嵌套属性结构

### componentProps

组件属性配置，类型为FormSchemaBase的componentProps与DesignerDynamicProps的交集
包含组件特有的属性，如Input的placeholder、Select的options等
支持动态属性配置

### componentEvent

组件事件配置，类型为DesignerDynamicProps
键名为事件名，值为ResolverValue类型的事件处理函数配置
例如: change、click、blur等事件

### formItemProps

表单项属性配置，类型为FormSchemaBase的formItemProps与DesignerDynamicProps的交集
包含表单项的配置，如noLabel、labelPosition、autoRules等
支持动态属性配置

### layoutProps

布局属性配置，类型为FormSchemaBase的layoutProps与DesignerDynamicProps的交集
包含组件的布局配置，如span、alone等
支持动态属性配置

### outsideProps

外部属性配置，类型为FormSchemaBase的outsideProps与DesignerDynamicProps的交集
包含组件外层的包装配置，如enable、direction、style等
支持动态属性配置

### insideProps

内部属性配置，包含renders等插槽配置
renders类型为DesignerDynamicProps，用于配置组件的插槽内容

## 子组件配置

children: 子组件数组，类型为DesignerFormSchema[]
用于容器型组件，如Group、Step等
支持多级嵌套

## 设计器内部属性

__d_locked: 组件是否被锁定，布尔类型
锁定后的组件不可编辑和删除
设计器内部使用，不影响运行时

## 使用示例

基础组件配置示例：
```
{
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

动态属性配置示例：
```
{
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

## 注意事项

DesignerFormSchema会被转换为FormSchemaBase用于运行时渲染
动态属性通过schema-resolver工具函数进行解析和转换
配置错误可能导致组件无法正常渲染，需注意数据结构的正确性
