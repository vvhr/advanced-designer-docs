title: Autocomplete组件
description: Autocomplete自动补全输入框组件的用途、默认参数和可配置项说明
keywords: Autocomplete,自动补全,输入提示,组件配置
category: 组件菜单类

# Autocomplete组件

## 组件概述

Autocomplete是输入型组件，提供输入建议功能。用户输入时自动显示匹配的建议选项。

## 组件类型

type: Inputer
component: Autocomplete
menuRootKey: inputer

## 默认参数

key: 空字符串（默认使用field值）
field: 空字符串（需手动设置）
type: Inputer
label: 新建自动补全
hidden: false
value: 空字符串
component: Autocomplete
componentProps:
  disabled: false
  clearable: false
  style: 空对象
  placeholder: null
  valueKey: value
  debounce: 300
  placement: bottom-start
  fetchSuggestions: [预配置的建议选项数组]
  triggerOnFocus: true
  selectWhenUnmatched: false
  highlightFirstItem: false
  fitInputWidth: false
componentEvent:
  _d_onSelect: [动态事件配置]
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
component: 组件名称（固定为Autocomplete）
hidden: 是否隐藏组件

### 组件属性（componentProps）

value: 组件默认值（字符串类型）
disabled: 是否禁用
clearable: 是否显示清除按钮
style: 自定义样式对象
placeholder: 输入框占位符
valueKey: 建议选项的值字段名
debounce: 输入防抖延迟时间（毫秒）
placement: 建议列表的弹出位置
fetchSuggestions: 获取建议的函数或建议选项数组
triggerOnFocus: 获得焦点时是否触发建议
selectWhenUnmatched: 输入不匹配时是否允许选择
highlightFirstItem: 是否高亮第一个选项
fitInputWidth: 建议列表宽度是否与输入框一致

### 事件配置

onSelect: 选择建议项时触发（支持动态配置）

### 表单项属性（formItemProps）

noLabel: 是否不显示标签
labelPosition: 标签位置（left、right、top）
subLabel: 副标签文本
autoRules: 自动校验规则数组

### 布局属性（layoutProps）

span: 栅格占据的列数（1-24）
alone: 是否独占一行

## 使用场景

搜索输入: 提供搜索建议
地址输入: 输入地址时提供地址建议
自动补全: 输入时自动补全内容

## 注意事项

field属性是必填的，用于数据绑定
fetchSuggestions可以是数组或函数
可通过debounce控制输入防抖延迟
支持动态配置onSelect事件处理函数
