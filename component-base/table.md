title: Table组件
description: Table表格组件的用途、默认参数和可配置项说明
keywords: Table,表格,表格组件,组件配置
category: 组件菜单类

# Table组件

## 组件概述

Table是输入型组件，用于展示和编辑表格数据。支持行内编辑、操作列、动态添加删除行等功能，用于复杂的数据录入场景。

## 组件类型

type: Inputer
component: Table
menuRootKey: inputer

## 默认参数

key: 空字符串（默认使用field值）
field: 空字符串（需手动设置）
type: Inputer
label: 新建表格
hidden: false
value: []
component: Table
componentProps:
  columns: [预配置的列定义数组，包含姓名、年龄、性别、地址、电话、操作等列]
  disabled: false
  ellipsis: false
  align: left
  headerAlign: left
  rowKey: id
  emptyValue: -
  adaptive: false
  border: true
componentEvent:
  _d_onAction: [动态事件配置，处理删除等操作]
formItemProps:
  noLabel: false
  labelPosition: right
  subLabel: 空字符串
  autoRules: 空数组
layoutProps:
  span: 24
  alone: true
outsideProps:
  enable: true
  direction: column
  style: {gap: 10px}
  _d_prependRender: [动态前置渲染配置，添加按钮]

## 可配置项

### 基本属性

key: 组件唯一标识符（默认使用field值）
field: 表单字段名，用于数据绑定（必填）
type: 组件类型（固定为Inputer）
component: 组件名称（固定为Table）
hidden: 是否隐藏组件

### 组件属性（componentProps）

value: 组件默认值（数组类型，存储表格行数据）
columns: 列定义数组，每列包含以下属性
  key: 列的唯一标识
  field: 数据字段名
  label: 列标题
  editable: 是否可编辑
  editProps: 编辑配置
    defaultValue: 默认值
    component: 编辑组件类型
    componentProps: 编辑组件属性
    formItemProps: 编辑组件的表单项属性
  type: 列类型，如action表示操作列
  typeProps: 列类型特定属性
  fixed: 固定位置，如right表示固定在右侧
disabled: 是否禁用整个表格
ellipsis: 是否显示省略号
align: 列对齐方式，可选值包括left、center、right
headerAlign: 表头对齐方式
rowKey: 行的唯一标识字段名
emptyValue: 空值显示文本
adaptive: 是否自适应
border: 是否显示边框

### 事件配置

onAction: 操作列点击时触发（支持动态配置）
事件参数包含row、index、name等信息

### 前置渲染配置

outsideProps._d_prependRender: 表格前置内容渲染
默认配置添加按钮，用于添加新行
支持动态配置，可自定义添加逻辑

### 表单项属性（formItemProps）

noLabel: 是否不显示标签
labelPosition: 标签位置（left、right、top）
subLabel: 副标签文本
autoRules: 自动校验规则数组

### 布局属性（layoutProps）

span: 栅格占据的列数（1-24），默认24
alone: 是否独占一行，默认true

## 使用场景

动态表格: 需要动态添加删除行的表格数据录入
复杂表单: 包含多个字段的表格形式表单
数据列表: 展示和编辑列表数据

## 注意事项

field属性是必填的，用于数据绑定
value为数组类型，存储表格行数据数组
每行数据为对象，字段名对应columns中定义的field
支持行内编辑，每列可配置不同的编辑组件
可通过outsideProps配置前置内容，如添加按钮
默认alone为true，独占一行
