title: Input组件
description: Input输入框组件的用途、默认参数和可配置项说明
keywords: Input,输入框,输入型组件,组件配置
category: 组件菜单类

# Input组件

## 组件概述

Input是输入型组件，用于通过鼠标或键盘输入字符。支持文本、多行文本、密码等多种输入类型。

## 组件类型

type: Inputer
component: Input
menuRootKey: inputer

## 默认参数

key: 空字符串（默认使用field值）
field: 空字符串（需手动设置）
type: Inputer
label: 新建输入框
hidden: false
value: 空字符串
component: Input
componentProps:
  type: text
  disabled: false
  clearable: false
  showPassword: false
  showWordLimit: false
  placeholder: null
  maxlength: null
  minlength: null
  readonly: false
  autofocus: false
  autocomplete: off
  validateEvent: true
  resize: none
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
component: 组件名称（固定为Input）
hidden: 是否隐藏组件
_d_hidden: 动态隐藏配置（ResolverValue类型）

### 标题属性

label: 组件标签文本
_d_label: 动态标签配置（ResolverValue类型）
subLabel: 副标签文本
noLabel: 是否不显示标签
labelPosition: 标签位置（left、right、top）
labelWidth: 标签宽度
labelMaxWidth: 标签最大宽度
autoRules: 自动校验规则数组
_d_rules: 动态校验规则配置（ResolverValue类型）

### 组件属性（componentProps）

value: 组件默认值
_d_value: 动态值配置（ResolverValue类型）
disabled: 是否禁用
_d_disabled: 动态禁用配置（ResolverValue类型）
clearable: 是否显示清除按钮
placeholder: 输入框占位符文本
type: 输入框类型，可选值包括text、textarea、password
showPassword: 是否显示密码切换按钮（type为password时）
showWordLimit: 是否显示字数统计（type为textarea时）
maxlength: 最大输入长度
minlength: 最小输入长度
readonly: 是否只读
autofocus: 是否自动聚焦
autocomplete: 自动完成属性
validateEvent: 是否触发表单校验
resize: 文本域大小调整，可选值包括none、both、horizontal、vertical

### 表单项属性（formItemProps）

noLabel: 是否不显示标签
labelPosition: 标签位置（left、right、top）
subLabel: 副标签文本
autoRules: 自动校验规则数组，如isRequired、noSpace等

### 布局属性（layoutProps）

span: 栅格占据的列数（1-24）
alone: 是否独占一行

## 事件配置

Input组件支持以下事件：
change: 值改变时触发
blur: 失去焦点时触发
focus: 获得焦点时触发
clear: 点击清除按钮时触发

## 插槽配置

Input组件支持以下插槽：
prefix: 输入框头部内容
suffix: 输入框尾部内容
prepend: 输入框前置内容
append: 输入框后置内容

## 使用场景

文本输入: 输入用户名、姓名等文本信息
多行文本: 输入备注、描述等多行文本
密码输入: 输入密码等敏感信息
搜索框: 实现搜索功能

## 注意事项

field属性是必填的，用于数据绑定
可通过autoRules配置自动校验规则
支持动态属性配置，实现灵活的表单逻辑
