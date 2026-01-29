title: Alert组件
description: Alert提示组件的用途、默认参数和可配置项说明
keywords: Alert,提示组件,装饰型组件,组件配置
category: 组件菜单类

# Alert组件

## 组件概述

Alert是装饰型组件，用于在表单中显示提示信息。不参与表单数据收集，仅用于展示和装饰。

## 组件类型

type: Decorator
component: Alert
menuRootKey: decorator

## 默认参数

key: 空字符串（需手动设置）
field: 空字符串（装饰型组件不需要）
type: Decorator
label: 新建提示
hidden: false
component: Alert
componentProps:
  title: 提示
  type: primary
  description: 这是一条提示信息
  closable: false
  center: false
  closeText: 空字符串
  showIcon: true
  effect: light
  style: 空对象
layoutProps:
  span: 12
  alone: false

## 可配置项

### 基本属性

key: 组件唯一标识符
type: 组件类型（固定为Decorator）
component: 组件名称（固定为Alert）
hidden: 是否隐藏组件
_d_hidden: 动态隐藏配置（ResolverValue类型）

### 组件属性（componentProps）

title: 提示标题文本
type: 提示类型，可选值包括primary、success、warning、error、info
description: 提示描述文本
closable: 是否显示关闭按钮
center: 文字是否居中
closeText: 关闭按钮文本
showIcon: 是否显示图标
effect: 主题样式，可选值包括light、dark
style: 自定义样式对象

### 布局属性（layoutProps）

span: 栅格占据的列数（1-24）
alone: 是否独占一行

### 外部属性（outsideProps）

enable: 是否启用外层包装
direction: 包装方向（row、column）
style: 自定义样式对象

## 事件配置

Alert组件支持配置事件处理函数，通过componentEvent配置。

## 使用场景

表单提示: 在表单中显示重要提示信息
操作反馈: 显示操作成功或失败的提示
注意事项: 提醒用户注意某些重要信息

## 注意事项

Alert是装饰型组件，不参与表单数据收集
组件没有field属性，不需要绑定表单数据
可通过hidden属性动态控制显示和隐藏
