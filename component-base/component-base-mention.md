title: Mention组件
description: Mention提及输入框组件的用途、默认参数和可配置项说明
keywords: Mention,提及输入,@提及,组件配置
category: 组件菜单类

# Mention组件

## 组件概述

Mention是输入型组件，用于在输入框中提及用户或实体。通过输入触发字符（如@）显示建议列表，选择后插入提及内容。

## 组件类型

type: Inputer
component: Mention
menuRootKey: inputer

## 默认参数

key: 空字符串（默认使用field值）
field: 空字符串（需手动设置）
type: Inputer
label: 新建提及输入框
hidden: false
value: 空字符串
component: Mention
componentProps:
  disabled: false
  trigger: @
  placement: bottom
  options: []
  type: text
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
component: 组件名称（固定为Mention）
hidden: 是否隐藏组件

### 组件属性（componentProps）

value: 组件默认值（字符串类型）
disabled: 是否禁用
trigger: 触发字符，默认@
placement: 建议列表弹出位置，可选值包括top、bottom等
options: 建议选项数组，包含用户或实体信息
type: 输入框类型，可选值包括text、textarea

### 表单项属性（formItemProps）

noLabel: 是否不显示标签
labelPosition: 标签位置（left、right、top）
subLabel: 副标签文本
autoRules: 自动校验规则数组

### 布局属性（layoutProps）

span: 栅格占据的列数（1-24）
alone: 是否独占一行

## 事件配置

Mention组件支持以下事件：
change: 值改变时触发
select: 选择提及项时触发

## 使用场景

用户提及: 在输入框中提及用户
实体提及: 提及话题、标签等实体
评论系统: 在评论中提及其他用户

## 注意事项

field属性是必填的，用于数据绑定
可通过trigger配置触发字符，默认为@
可通过options配置建议选项列表
支持text和textarea两种输入类型
