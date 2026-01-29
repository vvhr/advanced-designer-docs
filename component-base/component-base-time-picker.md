title: TimePicker组件
description: TimePicker时刻面板选择框组件的用途、默认参数和可配置项说明
keywords: TimePicker,时间选择,时刻选择,组件配置
category: 组件菜单类

# TimePicker组件

## 组件概述

TimePicker是输入型组件，用于选择或输入时间。通过时间面板选择时间，支持时间范围选择。

## 组件类型

type: Inputer
component: TimePicker
menuRootKey: inputer

## 默认参数

key: 空字符串（默认使用field值）
field: 空字符串（需手动设置）
type: Inputer
label: 新建时刻面板选择框
hidden: false
value: null
component: TimePicker
componentProps:
  disabled: false
  editable: true
  clearable: false
  placeholder: null
  startPlaceholder: 开始时间
  endPlaceholder: 结束时间
  isRange: false
  arrowControl: false
  format: HH:mm:ss
  valueFormat: HH:mm:ss
  rangeSeparator: -
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
component: 组件名称（固定为TimePicker）
hidden: 是否隐藏组件

### 组件属性（componentProps）

value: 组件默认值（时间范围时为数组）
disabled: 是否禁用
editable: 输入框是否可编辑
clearable: 是否显示清除按钮
placeholder: 输入框占位符
startPlaceholder: 范围选择时开始时间的占位符
endPlaceholder: 范围选择时结束时间的占位符
isRange: 是否为时间范围选择
arrowControl: 是否使用箭头进行时间选择
format: 显示在输入框中的格式
valueFormat: 可选值的格式
rangeSeparator: 范围选择时分隔符

### 表单项属性（formItemProps）

noLabel: 是否不显示标签
labelPosition: 标签位置（left、right、top）
subLabel: 副标签文本
autoRules: 自动校验规则数组

### 布局属性（layoutProps）

span: 栅格占据的列数（1-24）
alone: 是否独占一行

## 事件配置

TimePicker组件支持以下事件：
change: 时间值改变时触发
blur: 失去焦点时触发
focus: 获得焦点时触发

## 使用场景

时间选择: 选择具体的时间点
时间范围: 选择时间范围
时间输入: 通过输入框输入时间

## 注意事项

field属性是必填的，用于数据绑定
时间范围选择时value为数组类型
可通过format和valueFormat配置时间格式
支持通过箭头控制时间选择
