title: GenderRadio组件
description: GenderRadio性别选择快捷示例组件的用途和默认参数说明
keywords: GenderRadio,性别选择,快捷组件,示例组件
category: 组件菜单类

# GenderRadio组件

## 组件概述

GenderRadio是快捷示例组件，基于Radio组件封装，专门用于性别选择场景。已预配置性别选项和校验规则。

## 组件类型

type: Inputer
component: Radio
menuRootKey: demo

## 默认参数

key: 空字符串（默认使用field值）
field: gender
type: Inputer
label: 性别
hidden: false
value: 空字符串
component: Radio
componentProps:
  disabled: false
  clearable: false
  options: [{value: 1, label: 男, disabled: false, border: true}, {value: 2, label: 女, disabled: false, border: true}]
  optionKeys: {label: label, value: value, children: children, disabled: disabled}
  style: 空对象
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

field: 默认为gender，适合性别字段
label: 默认为性别，符合业务场景

### 选项配置

options: 预配置两个选项，值为1（男）和2（女）
每个选项包含value、label、disabled、border属性
border属性设置为true，显示边框样式

### 校验规则

autoRules: 预配置isRequired（必填）规则

### 组件属性

基于Radio组件，保持Radio的所有功能
可根据需要修改componentProps中的属性

## 使用场景

用户注册: 在用户注册表单中快速添加性别选择
个人信息: 在个人信息编辑表单中使用
用户资料: 在用户资料表单中使用

## 自定义配置

GenderRadio组件可以像普通Radio组件一样进行配置
可以修改label、field、componentProps等所有属性
可以修改options数组添加更多选项或修改选项值
可以添加更多校验规则或事件处理函数

## 注意事项

GenderRadio是基于Radio组件的快捷组件，功能与Radio相同
预配置的选项值为1和2，可根据业务需求修改
建议根据实际业务场景修改field和label属性
