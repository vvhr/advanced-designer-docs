title: Divider组件
description: Divider分隔线组件的用途、默认参数和可配置项说明
keywords: Divider,分隔线,装饰型组件,组件配置
category: 组件菜单类

# Divider组件

## 组件概述

Divider是装饰型组件，用于在表单中显示分隔线。用于分隔内容区域，提升表单的可读性。不参与表单数据收集，仅用于展示和装饰。

## 组件类型

type: Decorator
component: Divider
menuRootKey: decorator

## 默认参数

key: 空字符串（需手动设置）
field: 空字符串（装饰型组件不需要）
type: Decorator
label: 新建分隔线
component: Divider
componentProps:
  direction: horizontal
  borderStyle: solid
  contentPosition: center
layoutProps:
  span: 12
  alone: false
insideProps:
  renders:
    _d_default: [动态插槽配置，默认显示我是一条分隔线]

## 可配置项

### 基本属性

key: 组件唯一标识符
type: 组件类型（固定为Decorator）
component: 组件名称（固定为Divider）
hidden: 是否隐藏组件

### 组件属性（componentProps）

direction: 分隔线方向，可选值包括horizontal（水平）、vertical（垂直）
borderStyle: 分隔线样式，可选值包括solid、dashed、dotted
contentPosition: 分隔线内容位置，可选值包括left、center、right

### 插槽配置

insideProps.renders._d_default: 分隔线内容插槽
可通过动态配置显示自定义内容
默认显示我是一条分隔线

### 布局属性（layoutProps）

span: 栅格占据的列数（1-24）
alone: 是否独占一行

## 使用场景

内容分隔: 分隔表单中的不同内容区域
视觉分组: 通过分隔线进行视觉分组
表单美化: 提升表单的可读性和美观度

## 注意事项

Divider是装饰型组件，不参与表单数据收集
组件没有field属性，不需要绑定表单数据
可通过插槽配置自定义分隔线内容
支持水平和垂直两种方向
