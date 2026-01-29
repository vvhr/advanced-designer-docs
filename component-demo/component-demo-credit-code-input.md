title: CreditCodeInput组件
description: CreditCodeInput信用代码输入快捷示例组件的用途和默认参数说明
keywords: CreditCodeInput,信用代码,快捷组件,示例组件
category: 组件菜单类

# CreditCodeInput组件

## 组件概述

CreditCodeInput是快捷示例组件，基于Input组件封装，专门用于信用代码输入场景。已预配置信用代码相关的校验规则和属性。

## 组件类型

type: Inputer
component: Input
menuRootKey: demo

## 默认参数

key: 空字符串（默认使用field值）
field: creditCode
type: Inputer
label: 信用代码
hidden: false
value: 空字符串
component: Input
componentProps:
  type: text
  disabled: false
  clearable: false
  showPassword: false
  showWordLimit: true
  placeholder: null
  maxlength: 18
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
  autoRules: [isRequired, isCreditCode]
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

field: 默认为creditCode，适合信用代码字段
label: 默认为信用代码，符合业务场景

### 校验规则

autoRules: 预配置isRequired（必填）和isCreditCode（信用代码格式校验）规则
maxlength: 预设置为18，限制信用代码最大长度
showWordLimit: 预设置为true，显示字数统计

### 组件属性

基于Input组件，保持Input的所有功能
可根据需要修改componentProps中的属性

## 使用场景

企业注册: 在企业注册表单中快速添加信用代码输入框
企业信息: 在企业信息编辑表单中使用
资质认证: 在资质认证表单中使用

## 自定义配置

CreditCodeInput组件可以像普通Input组件一样进行配置
可以修改label、field、componentProps等所有属性
可以添加更多校验规则或事件处理函数

## 注意事项

CreditCodeInput是基于Input组件的快捷组件，功能与Input相同
预配置的isCreditCode校验规则会自动校验信用代码格式
建议根据实际业务场景修改field和label属性
