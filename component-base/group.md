title: Group组件
description: Group分组卡片组件的用途、默认参数和可配置项说明
keywords: Group,分组卡片,容器组件,组件配置
category: 组件菜单类

# Group组件

## 组件概述

Group是容器型组件，提供一种具有模块标题的分组容器，可将子组件容纳在其中，支持折叠展开。用于表单内容的逻辑分组和视觉分组。

## 组件类型

type: Container
component: Group
menuRootKey: container

## 默认参数

key: 空字符串（需手动设置）
type: Container
label: 新建卡片分组
hidden: false
component: Group
componentProps:
  toggleable: true
  expand: true
  headerStyle: 空对象
  bodyStyle: 空对象
  labelStyle: 空对象
  subLabelStyle: 空对象
layoutProps:
  span: 24
  alone: true
children: []

## 可配置项

### 基本属性

key: 组件唯一标识符（必填）
type: 组件类型（固定为Container）
component: 组件名称（固定为Group）
hidden: 是否隐藏组件
label: 分组标题

### 组件属性（componentProps）

toggleable: 是否可折叠，默认true
expand: 是否默认展开，默认true
headerStyle: 头部样式对象
bodyStyle: 内容区域样式对象
labelStyle: 标题样式对象
subLabelStyle: 副标题样式对象

### 表单项属性（formItemProps）

subLabel: 副标题文本

### 布局属性（layoutProps）

span: 栅格占据的列数（1-24），默认24
alone: 是否独占一行，默认true

### 子组件配置

children: 子组件数组，类型为DesignerFormSchema[]
用于容纳其他组件，支持多级嵌套

## 使用场景

表单分组: 将表单内容按逻辑分组
折叠展开: 通过折叠展开功能管理大量内容
视觉分组: 通过卡片样式进行视觉分组

## 注意事项

Group是容器型组件，不参与表单数据收集
组件没有field属性，不需要绑定表单数据
可通过children属性添加子组件
支持折叠展开功能，便于管理大量内容
默认alone为true，独占一行
