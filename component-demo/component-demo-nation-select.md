title: NationSelect组件
description: NationSelect民族选择快捷示例组件的用途和默认参数说明
keywords: NationSelect,民族选择,快捷组件,示例组件
category: 组件菜单类

# NationSelect组件

## 组件概述

NationSelect是快捷示例组件，基于Select组件封装，专门用于民族选择场景。已预配置56个民族选项和校验规则。

## 组件类型

type: Inputer
component: Select
menuRootKey: demo

## 默认参数

key: 空字符串（默认使用field值）
field: nation
type: Inputer
label: 民族
hidden: false
value: 空字符串
component: Select
componentProps:
  disabled: false
  clearable: false
  placeholder: null
  multiple: false
  collapseTags: false
  collapseTagsTooltip: false
  multipleLimit: 0
  autocomplete: off
  filterable: false
  allowCreate: false
  noMatchText: 无匹配数据
  noDataText: 无数据
  reserveKeyword: true
  defaultFirstOption: false
  popperAppendToBody: true
  automaticDropdown: false
  options: [56个民族选项，包含汉族、蒙古族、回族等，值从01到98]
componentEvent: 空对象
formItemProps:
  noLabel: false
  labelPosition: right
  subLabel: 空字符串
  autoRules: [isRequired]
layoutProps:
  span: 12
  alone: false
insideProps: 空对象
outsideProps:
  enable: false
  direction: row
  style: 空对象

## 预配置特性

### 字段配置

field: 默认为nation，适合民族字段
label: 默认为民族，符合业务场景

### 选项配置

options: 预配置56个民族选项，值从01到98
包含汉族、蒙古族、回族、藏族等所有民族
值格式为两位数字字符串，如01、02等
包含其他和外国血统中国籍人士选项

### 校验规则

autoRules: 预配置isRequired（必填）规则

### 组件属性

基于Select组件，保持Select的所有功能
可根据需要修改componentProps中的属性

## 使用场景

用户注册: 在用户注册表单中快速添加民族选择
个人信息: 在个人信息编辑表单中使用
人口统计: 在人口统计表单中使用

## 自定义配置

NationSelect组件可以像普通Select组件一样进行配置
可以修改label、field、componentProps等所有属性
可以修改options数组添加或删除民族选项
可以启用filterable实现搜索功能
可以添加更多校验规则或事件处理函数

## 注意事项

NationSelect是基于Select组件的快捷组件，功能与Select相同
预配置的民族选项值格式为两位数字字符串
建议根据实际业务场景修改field和label属性
