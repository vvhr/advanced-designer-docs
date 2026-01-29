title: InputNumber组件
description: InputNumber数值输入框组件的用途、默认参数和可配置项说明
keywords: InputNumber,数值输入,数字输入,组件配置
category: 组件菜单类

# InputNumber组件

## 组件概述

InputNumber是输入型组件，仅允许输入标准的数字值，可定义范围。用于输入数字类型的表单字段。

## 组件类型

type: Inputer
component: InputNumber
menuRootKey: inputer

## 默认参数

key: 空字符串（默认使用field值）
field: 空字符串（需手动设置）
type: Inputer
label: 新建数值输入框
hidden: false
value: null
component: InputNumber
componentProps:
  disabled: false
  min: null
  max: null
  step: 1
  stepStrictly: false
  precision: null
  controls: false
  controlsPosition: 空字符串
  placeholder: null
  validateEvent: true
  align: left
  style: {width: 100%}
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
component: 组件名称（固定为InputNumber）
hidden: 是否隐藏组件

### 组件属性（componentProps）

value: 组件默认值（数字类型或null）
disabled: 是否禁用
min: 最小值，null表示不限制
max: 最大值，null表示不限制
step: 步长，默认1
stepStrictly: 是否只能输入step的倍数
precision: 精度，保留小数位数，null表示不限制
controls: 是否显示控制按钮
controlsPosition: 控制按钮位置，可选值包括right、left
placeholder: 输入框占位符
validateEvent: 是否触发表单校验
align: 对齐方式，可选值包括left、center、right
style: 自定义样式对象

### 表单项属性（formItemProps）

noLabel: 是否不显示标签
labelPosition: 标签位置（left、right、top）
subLabel: 副标签文本
autoRules: 自动校验规则数组

### 布局属性（layoutProps）

span: 栅格占据的列数（1-24）
alone: 是否独占一行

## 事件配置

InputNumber组件支持以下事件：
change: 值改变时触发
blur: 失去焦点时触发
focus: 获得焦点时触发

## 使用场景

数字输入: 输入年龄、数量、金额等数字
范围限制: 通过min和max限制输入范围
精度控制: 通过precision控制小数位数

## 注意事项

field属性是必填的，用于数据绑定
value为数字类型或null
可通过min和max设置取值范围
可通过precision设置小数位数
可通过step设置步长，控制增减幅度
