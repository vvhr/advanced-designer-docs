title: PhoneInput组件
description: PhoneInput手机号码输入快捷示例组件的用途和默认参数说明
keywords: PhoneInput,手机号输入,快捷组件,示例组件
category: 组件菜单类

# PhoneInput组件

## 组件概述

PhoneInput是快捷示例组件，基于Input组件封装，专门用于手机号码输入场景。已预配置手机号相关的校验规则和属性。

## 组件类型

type: Inputer
component: Input
menuRootKey: demo

## 默认参数

key: 空字符串（默认使用field值）
field: phone
type: Inputer
label: 手机号码
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
  maxlength: 11
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
  autoRules: [isRequired, isMobilePhone]
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

field: 默认为phone，适合手机号字段
label: 默认为手机号码，符合业务场景

### 校验规则

autoRules: 预配置isRequired（必填）和isMobilePhone（手机号格式校验）规则
maxlength: 预设置为11，限制手机号最大长度
showWordLimit: 预设置为true，显示字数统计

### 组件属性

基于Input组件，保持Input的所有功能
可根据需要修改componentProps中的属性

## 使用场景

用户注册: 在用户注册表单中快速添加手机号输入框
联系方式: 在联系方式表单中使用
短信验证: 在短信验证码表单中使用

## 自定义配置

PhoneInput组件可以像普通Input组件一样进行配置
可以修改label、field、componentProps等所有属性
可以添加更多校验规则或事件处理函数

## 注意事项

PhoneInput是基于Input组件的快捷组件，功能与Input相同
预配置的isMobilePhone校验规则会自动校验手机号格式
建议根据实际业务场景修改field和label属性
