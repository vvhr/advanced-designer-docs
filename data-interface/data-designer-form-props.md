title: DesignerFormProps数据结构
description: DesignerFormProps核心数据结构说明，定义表单设计器提供的表单设置配置结构
keywords: DesignerFormProps,表单属性,表单配置,全局配置
category: 数据结构类

# DesignerFormProps数据结构

## 概述

DesignerFormProps定义了表单设计器提供的表单全局属性配置，影响整个表单的展示和行为。这些属性会传递给AeForm组件。

## 属性说明

### stepValue

类型: number | null
说明: 当表单类型为分步表单时，设置当前激活的步骤索引
默认值: null
用途: 控制分步表单的当前步骤

### disabled

类型: boolean
说明: 是否禁用整个表单
默认值: false
用途: 禁用后所有组件不可交互

### type

类型: 'form' | 'desc'
说明: 表单类型，form为表单模式用于数据录入，desc为描述列表模式用于数据展示
默认值: 'form'
用途: 控制表单的展示模式

### size

类型: 'small' | 'default' | 'large'
说明: 表单尺寸，控制表单组件的整体尺寸
默认值: 'default'
用途: 统一控制表单组件的尺寸

### designable

类型: boolean
说明: 是否启用设计模式
默认值: true
用途: 设计模式下显示组件边框和操作手柄

### schemaProps

类型: FormSchemaProps
说明: 表单的SchemaProps配置，包含更多高级表单属性
默认值: undefined
用途: 配置表单的高级属性

### labelWidth

类型: string | number
说明: 表单标签的宽度
默认值: undefined
用途: 设置表单标签的统一宽度，支持像素值或百分比

### showErrorNotice

类型: boolean
说明: 是否在表单提交校验失败时显示错误提示信息
默认值: true
用途: 控制错误提示的显示

### autoInitField

类型: boolean
说明: 是否自动初始化表单字段的默认值
默认值: false
用途: 控制字段的自动初始化行为

## 使用示例

基础配置示例：
```
{
  type: 'form',
  size: 'default',
  disabled: false,
  labelWidth: '120px',
  showErrorNotice: true,
  autoInitField: false
}
```

分步表单配置示例：
```
{
  type: 'form',
  stepValue: 0,
  size: 'default',
  disabled: false
}
```

## 注意事项

DesignerFormProps会直接传递给AeForm组件
某些属性的修改会影响整个表单的行为
建议在表单设置面板中配置，避免直接编辑JSON
