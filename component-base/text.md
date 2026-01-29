title: Text组件
description: Text增强文本组件的用途、默认参数和可配置项说明
keywords: Text,文本组件,装饰型组件,组件配置
category: 组件菜单类

# Text组件

## 组件概述

Text是装饰型组件，用于在表单中显示增强文本内容。支持高亮、图标、样式等丰富的文本展示功能。不参与表单数据收集，仅用于展示和装饰。

## 组件类型

type: Decorator
component: Text
menuRootKey: decorator

## 默认参数

key: 空字符串（需手动设置）
field: 空字符串（装饰型组件不需要）
type: Decorator
label: 新建提示
component: Text
componentProps:
  value: 这是您应该配置的文本内容，您可以配置高亮、图标、样式等。
  icon: 空字符串
  iconStyle: 空对象
  dotType: 空字符串
  block: false
  patterns: [高亮, 图标, 样式]
  hlStyle: 空对象
  truncate: false
  expandable: false
  expandText: 展开
  collapseText: 收起
  copyable: false
  copyIcon: ep:document-copy
  copySuccessText: 复制成功
layoutProps:
  span: 12
  alone: false

## 可配置项

### 基本属性

key: 组件唯一标识符
type: 组件类型（固定为Decorator）
component: 组件名称（固定为Text）
hidden: 是否隐藏组件

### 组件属性（componentProps）

value: 文本内容
icon: 图标名称
iconStyle: 图标样式对象
dotType: 点类型，可选值包括success、warning、error、info
block: 是否块级显示
patterns: 高亮关键词数组
hlStyle: 高亮样式对象
truncate: 是否截断文本
expandable: 是否可展开
expandText: 展开按钮文本
collapseText: 收起按钮文本
copyable: 是否可复制
copyIcon: 复制图标名称
copySuccessText: 复制成功提示文本

### 布局属性（layoutProps）

span: 栅格占据的列数（1-24）
alone: 是否独占一行

## 使用场景

文本展示: 在表单中显示说明文字、提示信息等
高亮文本: 通过patterns配置高亮关键词
可复制文本: 通过copyable配置可复制的文本内容
可展开文本: 通过expandable配置可展开的长文本

## 注意事项

Text是装饰型组件，不参与表单数据收集
组件没有field属性，不需要绑定表单数据
可通过patterns数组配置需要高亮的关键词
