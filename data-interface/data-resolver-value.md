title: ResolverValue数据结构
description: ResolverValue核心数据结构说明，定义表单设计器的抽象函数可视化配置引擎的数据结构
keywords: ResolverValue,动态属性,解析器,函数配置
category: 数据结构类

# ResolverValue数据结构

## 概述

ResolverValue是表单设计器中用于实现动态属性配置的核心数据结构。它通过抽象函数可视化配置引擎，将函数代码转换为可配置的动态属性。

## 结构定义

ResolverValue包含以下字段：

enable: 是否启用动态属性，布尔类型，默认false
value: 动态属性的值内容，任意类型，通常为函数代码字符串
prop: 实际字段名，字符串类型，默认从_d_前缀后的字段名截取
resolver: 解析方法类型，DesignResolver类型，默认使用FORM_SCHEMA_FN

## 解析方法类型

### FORM_SCHEMA_FN

类型标识: 'FORM_SCHEMA_FN'
说明: 字段支持FormSchemaFn动态值，使用FnEditor编辑
函数签名: (excontext: Recordable) => any
用途: 在表单Schema函数中使用，返回动态属性值
示例: _d_label、_d_hidden等属性

### COMPONENT_EVENT_FN

类型标识: 'COMPONENT_EVENT_FN'
说明: 字段支持ComponentEventFn动态值，使用FnEditor编辑
函数签名: (event: ComponentEvent, excontext: Recordable) => void
用途: 处理组件事件，如change、click等
示例: componentEvent中的事件处理函数

### IMMEDIATE_EXECUTE

类型标识: 'IMMEDIATE_EXECUTE'
说明: 字段不支持动态值也不支持常规类型，使用FnEditor自由编写
函数签名: () => any
用途: 执行立即执行的函数，返回任意值
示例: 某些特殊场景下的函数执行

### FORM_SCHEMA_DOM_FN

类型标识: 'FORM_SCHEMA_DOM_FN'
说明: 字段仅接收FormSchemaDomFn且需返回VNode，使用RenderDesigner编辑
函数签名: (excontext: Recordable) => VNode
用途: 返回VNode用于插槽渲染
示例: insideProps.renders中的插槽渲染函数

## 使用示例

### 动态标签配置

```
_d_label: {
  enable: true,
  value: '(excontext) => excontext.userName || "姓名"',
  prop: 'label',
  resolver: 'FORM_SCHEMA_FN'
}
```

### 动态隐藏配置

```
_d_hidden: {
  enable: true,
  value: '(excontext) => excontext.userRole === "admin"',
  prop: 'hidden',
  resolver: 'FORM_SCHEMA_FN'
}
```

### 事件处理函数配置

```
componentEvent: {
  change: {
    enable: true,
    value: '(event, excontext) => { console.log(event); excontext.handleChange(event); }',
    prop: 'change',
    resolver: 'COMPONENT_EVENT_FN'
  }
}
```

### 插槽渲染函数配置

```
insideProps: {
  renders: {
    prefix: {
      enable: true,
      value: '(excontext) => h("span", "前缀")',
      prop: 'prefix',
      resolver: 'FORM_SCHEMA_DOM_FN'
    }
  }
}
```

## 解析流程

设计器配置阶段: 用户通过可视化编辑器配置ResolverValue
Schema解析阶段: schema-resolver工具函数将ResolverValue转换为实际的函数
运行时执行: 在表单渲染时执行函数，获取动态值

## 注意事项

ResolverValue的value字段存储的是函数代码字符串
函数代码会在运行时通过new Function或eval执行，需注意安全性
prop字段用于指定实际字段名，如果不指定则从_d_前缀后截取
enable字段控制是否启用动态属性，false时使用静态值
