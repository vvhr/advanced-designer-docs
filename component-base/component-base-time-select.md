title: TimeSelect组件
description: TimeSelect时刻下拉选择框组件的用途、默认参数和可配置项说明
keywords: TimeSelect,时间选择,下拉选择,组件配置
category: 组件菜单类

# TimeSelect组件

## 组件概述

TimeSelect是输入型组件，用于选择时间。通过下拉列表选择时间，支持时间范围配置。

## 组件类型

type: Inputer
component: TimeSelect
menuRootKey: inputer

## 默认参数

key: 空字符串（默认使用field值）
field: 空字符串（需手动设置）
type: Inputer
label: 新建时刻下拉选择框
hidden: false
value: null
component: TimeSelect
componentProps:
  disabled: false
  clearable: false
  placeholder: null
  start: 09:00
  end: 18:00
  step: 00:30
  minTime: null
  maxTime: null
  format: HH:mm
  valueFormat: HH:mm
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
component: 组件名称（固定为TimeSelect）
hidden: 是否隐藏组件

### 组件属性（componentProps）

value: 组件默认值（时间字符串）
disabled: 是否禁用
clearable: 是否显示清除按钮
placeholder: 输入框占位符
start: 开始时间，默认09:00
end: 结束时间，默认18:00
step: 时间间隔，默认00:30
minTime: 最小可选时间
maxTime: 最大可选时间
format: 显示在输入框中的格式，默认HH:mm
valueFormat: 可选值的格式，默认HH:mm

### 表单项属性（formItemProps）

noLabel: 是否不显示标签
labelPosition: 标签位置（left、right、top）
subLabel: 副标签文本
autoRules: 自动校验规则数组

### 布局属性（layoutProps）

span: 栅格占据的列数（1-24）
alone: 是否独占一行

## 事件配置

TimeSelect组件支持以下事件：
change: 时间值改变时触发
blur: 失去焦点时触发
focus: 获得焦点时触发

## 使用场景

时间选择: 选择具体的时间点
营业时间: 选择营业时间段
预约时间: 选择预约时间

## 注意事项

field属性是必填的，用于数据绑定
可通过start和end设置可选时间范围
可通过step设置时间间隔
可通过minTime和maxTime进一步限制可选时间
