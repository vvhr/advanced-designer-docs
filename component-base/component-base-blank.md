title: Blank组件
description: Blank空白容器组件的用途、默认参数和可配置项说明
keywords: Blank,空白容器,容器组件,组件配置
category: 组件菜单类

# Blank组件

## 组件概述

Blank是容器型组件，提供一种视觉上不可见的分组容器，可将子组件容纳在其中便于统一管理。用于布局和分组，不显示任何视觉元素。

## 组件类型

type: Container
component: Blank
menuRootKey: container

## 默认参数

key: 空字符串（需手动设置）
field: 空字符串（容器型组件不需要）
type: Container
label: 新建空白容器
hidden: false
component: Blank
componentProps:
  style: 空对象
layoutProps:
  span: 24
  alone: true
children: []

## 可配置项

### 基本属性

key: 组件唯一标识符（必填）
type: 组件类型（固定为Container）
component: 组件名称（固定为Blank）
hidden: 是否隐藏组件
label: 容器标签（可选）

### 组件属性（componentProps）

style: 自定义样式对象，用于设置容器的样式

### 布局属性（layoutProps）

span: 栅格占据的列数（1-24），默认24
alone: 是否独占一行，默认true

### 子组件配置

children: 子组件数组，类型为DesignerFormSchema[]
用于容纳其他组件，支持多级嵌套

## 使用场景

布局分组: 将多个组件分组管理，便于统一操作
逻辑分组: 将相关组件组织在一起，提升可维护性
隐藏容器: 作为不可见的容器，不影响视觉展示

## 注意事项

Blank是容器型组件，不参与表单数据收集
组件没有field属性，不需要绑定表单数据
可通过children属性添加子组件
默认alone为true，独占一行，便于布局
