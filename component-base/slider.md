title: Slider组件
description: Slider滑块按钮组件的用途、默认参数和可配置项说明
keywords: Slider,滑块,滑块选择,组件配置
category: 组件菜单类

# Slider组件

## 组件概述

Slider是输入型组件，通过拖动滑块在一个固定区间内进行选择。支持单值和范围选择。

## 组件类型

type: Inputer
component: Slider
menuRootKey: inputer

## 默认参数

key: 空字符串（默认使用field值）
field: 空字符串（需手动设置）
type: Inputer
label: 新建滑块按钮
hidden: false
value: 0
component: Slider
componentProps:
  disabled: false
  min: 0
  max: 100
  step: 1
  showInput: false
  showInputControls: true
  showStops: false
  showTooltip: true
  range: false
  vertical: false
  height: null
  debounce: 300
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
component: 组件名称（固定为Slider）
hidden: 是否隐藏组件

### 组件属性（componentProps）

value: 组件默认值（范围选择时为数组）
disabled: 是否禁用
min: 最小值，默认0
max: 最大值，默认100
step: 步长，默认1
showInput: 是否显示输入框
showInputControls: 输入框是否显示控制按钮
showStops: 是否显示间断点
showTooltip: 是否显示提示信息
range: 是否为范围选择
vertical: 是否垂直方向
height: 垂直方向时的高度
debounce: 输入时的防抖延迟时间（毫秒）

### 表单项属性（formItemProps）

noLabel: 是否不显示标签
labelPosition: 标签位置（left、right、top）
subLabel: 副标签文本
autoRules: 自动校验规则数组

### 布局属性（layoutProps）

span: 栅格占据的列数（1-24）
alone: 是否独占一行

## 事件配置

Slider组件支持以下事件：
change: 值改变时触发
input: 拖拽时触发

## 使用场景

数值选择: 在一个范围内选择数值
范围选择: 选择数值范围
音量控制: 控制音量大小
进度设置: 设置进度值

## 注意事项

field属性是必填的，用于数据绑定
范围选择时value为数组类型
可通过min和max设置取值范围
可通过step设置步长，控制选择精度
