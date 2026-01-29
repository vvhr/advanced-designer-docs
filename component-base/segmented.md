title: Segmented组件
description: Segmented分段选择器组件的用途、默认参数和可配置项说明
keywords: Segmented,分段选择器,分段控件,组件配置
category: 组件菜单类

# Segmented组件

## 组件概述

Segmented是输入型组件，用于展示多个选项并允许用户选择其中一项。通过分段控件的形式展示选项，提供更好的视觉体验。

## 组件类型

type: Inputer
component: Segmented
menuRootKey: inputer

## 默认参数

key: 空字符串（默认使用field值）
field: 空字符串（需手动设置）
type: Inputer
label: 新建分段选择器
hidden: false
value: null
component: Segmented
componentProps:
  disabled: false
  options: [{label: 选项1, value: 1}, {label: 选项2, value: 2}, {label: 选项3, value: 3}]
componentEvent: 空对象
formItemProps:
  noLabel: false
  labelPosition: right
  subLabel: 空字符串
  autoRules: 空数组
layoutProps:
  span: 12
  alone: false
insideProps: 空对象
outsideProps:
  enable: false
  direction: row
  style: 空对象

## 可配置项

### 基本属性

key: 组件唯一标识符（默认使用field值）
field: 表单字段名，用于数据绑定（必填）
type: 组件类型（固定为Inputer）
component: 组件名称（固定为Segmented）
hidden: 是否隐藏组件

### 组件属性（componentProps）

value: 组件默认值（选中项的value值）
disabled: 是否禁用
options: 选项数组，每个选项包含label、value属性

### 表单项属性（formItemProps）

noLabel: 是否不显示标签
labelPosition: 标签位置（left、right、top）
subLabel: 副标签文本
autoRules: 自动校验规则数组

### 布局属性（layoutProps）

span: 栅格占据的列数（1-24）
alone: 是否独占一行

## 事件配置

Segmented组件支持以下事件：
change: 选中值变化时触发

## 使用场景

选项切换: 在多个选项之间切换
视图切换: 切换不同的视图模式
状态切换: 切换不同的状态

## 注意事项

field属性是必填的，用于数据绑定
value为选中项的value值
options数组中的value值类型需与表单数据类型一致
分段选择器提供更好的视觉体验，适合选项较少的场景
