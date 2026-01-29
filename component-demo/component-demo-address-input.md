title: AddressInput组件
description: AddressInput地址输入快捷示例组件的用途和默认参数说明
keywords: AddressInput,地址输入,快捷组件,示例组件
category: 组件菜单类

# AddressInput组件

## 组件概述

AddressInput是快捷示例组件，基于Input组件封装，专门用于地址输入场景。已预配置地址相关的校验规则和属性，使用多行文本输入。

## 组件类型

type: Inputer
component: Input
menuRootKey: demo

## 默认参数

key: 空字符串（默认使用field值）
field: address
type: Inputer
label: 地址
hidden: false
value: 空字符串
component: Input
componentProps:
  type: textarea
  disabled: false
  clearable: false
  showPassword: false
  showWordLimit: true
  rows: 4
  placeholder: null
  maxlength: 200
  minlength: null
  readonly: false
  autofocus: false
  autocomplete: off
  validateEvent: true
  resize: none
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

field: 默认为address，适合地址字段
label: 默认为地址，符合业务场景

### 输入类型

type: 预设置为textarea，使用多行文本输入
rows: 预设置为4，显示4行文本区域
maxlength: 预设置为200，限制地址最大长度
showWordLimit: 预设置为true，显示字数统计

### 校验规则

autoRules: 预配置isRequired（必填）规则

### 组件属性

基于Input组件，保持Input的所有功能
可根据需要修改componentProps中的属性

## 使用场景

用户注册: 在用户注册表单中快速添加地址输入框
收货地址: 在收货地址表单中使用
联系地址: 在联系地址表单中使用

## 自定义配置

AddressInput组件可以像普通Input组件一样进行配置
可以修改label、field、componentProps等所有属性
可以修改rows调整文本区域行数
可以修改maxlength调整最大长度限制
可以添加更多校验规则或事件处理函数

## 注意事项

AddressInput是基于Input组件的快捷组件，功能与Input相同
预配置为多行文本输入，适合地址等长文本输入场景
建议根据实际业务场景修改field和label属性
