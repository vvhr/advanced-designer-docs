title: InputTag组件
description: InputTag标签输入框组件的用途、默认参数和可配置项说明
keywords: InputTag,标签输入,标签组件,组件配置
category: 组件菜单类

# InputTag组件

## 组件概述

InputTag是输入型组件，通过输入内容创建标签。支持多个标签的输入和管理。

## 组件类型

type: Inputer
component: InputTag
menuRootKey: inputer

## 默认参数

key: 空字符串（默认使用field值）
field: 空字符串（需手动设置）
type: Inputer
label: 新建标签输入框
hidden: false
value: []
component: InputTag
componentProps:
  disabled: false
  clearable: false
  max: null
  tagType: info
  trigger: Enter
  draggable: false
  delimiter: null
  collapseTags: false
formItemProps:
  noLabel: false
  labelPosition: right
  subLabel: 空字符串
  autoRules: 空数组
layoutProps:
  span: 12
  alone: false

## 可配置项

### 基本属性

key: 组件唯一标识符（默认使用field值）
field: 表单字段名，用于数据绑定（必填）
type: 组件类型（固定为Inputer）
component: 组件名称（固定为InputTag）
hidden: 是否隐藏组件

### 组件属性（componentProps）

value: 组件默认值（数组类型，存储标签数组）
disabled: 是否禁用
clearable: 是否显示清除按钮
max: 最大标签数量，null表示不限制
tagType: 标签类型，可选值包括success、info、warning、danger
trigger: 触发创建标签的按键，可选值包括Enter、Space等
draggable: 标签是否可拖拽排序
delimiter: 分隔符，输入分隔符时自动创建标签
collapseTags: 超出max时是否折叠标签

### 表单项属性（formItemProps）

noLabel: 是否不显示标签
labelPosition: 标签位置（left、right、top）
subLabel: 副标签文本
autoRules: 自动校验规则数组

### 布局属性（layoutProps）

span: 栅格占据的列数（1-24）
alone: 是否独占一行

## 事件配置

InputTag组件支持以下事件：
change: 标签列表变化时触发
remove: 移除标签时触发

## 使用场景

标签输入: 输入多个标签，如技能标签、兴趣标签等
关键词输入: 输入多个关键词
分类选择: 通过标签进行分类

## 注意事项

field属性是必填的，用于数据绑定
value为数组类型，存储标签字符串数组
可通过max限制最大标签数量
可通过trigger配置触发创建标签的按键
可通过delimiter配置分隔符自动创建标签
