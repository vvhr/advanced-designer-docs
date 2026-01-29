title: Rate组件
description: Rate评分按钮组件的用途、默认参数和可配置项说明
keywords: Rate,评分,评分组件,组件配置
category: 组件菜单类

# Rate组件

## 组件概述

Rate是输入型组件，用于对事物进行评级操作。通过点击星星或其他图标进行评分。

## 组件类型

type: Inputer
component: Rate
menuRootKey: inputer

## 默认参数

key: 空字符串（默认使用field值）
field: 空字符串（需手动设置）
type: Inputer
label: 新建评分按钮
hidden: false
value: 0
component: Rate
componentProps:
  disabled: false
  max: 5
  allowHalf: false
  lowThreshold: 2
  highThreshold: 4
  showText: true
  showScore: false
  textColor: #1f2937
  texts: [极差, 差, 一般, 好, 极好]
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
component: 组件名称（固定为Rate）
hidden: 是否隐藏组件

### 组件属性（componentProps）

value: 组件默认值（数字类型，0-max之间）
disabled: 是否禁用
max: 最大评分值，默认5
allowHalf: 是否允许半选
lowThreshold: 低分和中等分数的界限值
highThreshold: 高分和中等分数的界限值
showText: 是否显示辅助文字
showScore: 是否显示当前分数
textColor: 辅助文字的颜色
texts: 辅助文字数组，长度为max

### 表单项属性（formItemProps）

noLabel: 是否不显示标签
labelPosition: 标签位置（left、right、top）
subLabel: 副标签文本
autoRules: 自动校验规则数组

### 布局属性（layoutProps）

span: 栅格占据的列数（1-24）
alone: 是否独占一行

## 事件配置

Rate组件支持以下事件：
change: 评分值改变时触发

## 使用场景

产品评价: 对产品进行评分
服务评价: 对服务质量进行评分
满意度调查: 在满意度调查表单中使用

## 注意事项

field属性是必填的，用于数据绑定
value为数字类型，范围在0到max之间
可通过texts数组自定义评分文字
支持半选功能，value可以是小数
