title: RadioButton组件
description: RadioButton单选按钮组组件的用途、默认参数和可配置项说明
keywords: RadioButton,单选按钮,单选组,组件配置
category: 组件菜单类

# RadioButton组件

## 组件概述

RadioButton是输入型组件，用于单选场景。通过单选按钮组的形式展示选项，支持从多个选项中选择一个值。

## 组件类型

type: Inputer
component: RadioButton
menuRootKey: inputer

## 默认参数

key: 空字符串（默认使用field值）
field: 空字符串（需手动设置）
type: Inputer
label: 新单选按钮
hidden: false
value: 空字符串
component: RadioButton
componentProps:
  disabled: false
  clearable: false
  options: [{value: 1, label: 选项1, disabled: false}, {value: 2, label: 选项2, disabled: false}]
  optionKeys: {label: label, value: value, children: children, disabled: disabled}
  style: 空对象
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
component: 组件名称（固定为RadioButton）
hidden: 是否隐藏组件

### 组件属性（componentProps）

value: 组件默认值（选中项的value值）
disabled: 是否禁用
clearable: 是否显示清除按钮
options: 选项数组，每个选项包含value、label、disabled属性
optionKeys: 选项对象的键名映射
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

RadioButton组件支持以下事件：
change: 选中值变化时触发

## 使用场景

单选场景: 从多个选项中选择一个值
性别选择: 选择性别等单选场景
状态选择: 选择状态、类型等

## 注意事项

field属性是必填的，用于数据绑定
value为选中项的value值，不是数组
options数组中的value值类型需与表单数据类型一致
可通过clearable配置清除按钮，允许清空选择
