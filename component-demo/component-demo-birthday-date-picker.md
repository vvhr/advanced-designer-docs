title: BirthdayDatePicker组件
description: BirthdayDatePicker出生日期选择快捷示例组件的用途和默认参数说明
keywords: BirthdayDatePicker,出生日期,快捷组件,示例组件
category: 组件菜单类

# BirthdayDatePicker组件

## 组件概述

BirthdayDatePicker是快捷示例组件，基于DatePicker组件封装，专门用于出生日期选择场景。已预配置日期相关的属性和校验规则。

## 组件类型

type: Inputer
component: DatePicker
menuRootKey: demo

## 默认参数

key: 空字符串（默认使用field值）
field: birthday
type: Inputer
label: 出生日期
hidden: false
value: null
component: DatePicker
componentProps:
  disabled: false
  editable: true
  clearable: false
  placeholder: null
  startPlaceholder: 开始时间
  endPlaceholder: 结束时间
  type: datetime
  format: YYYY-MM-DD
  valueFormat: YYYY-MM-DD HH:mm:ss
  rangeSeparator: -
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

field: 默认为birthday，适合出生日期字段
label: 默认为出生日期，符合业务场景

### 日期类型

type: 预设置为datetime，使用日期时间选择
format: 预设置为YYYY-MM-DD，显示格式
valueFormat: 预设置为YYYY-MM-DD HH:mm:ss，值格式

### 校验规则

autoRules: 预配置isRequired（必填）规则
value: 预设置为null，存储日期值

### 组件属性

基于DatePicker组件，保持DatePicker的所有功能
可根据需要修改componentProps中的属性

## 使用场景

用户注册: 在用户注册表单中快速添加出生日期选择
个人信息: 在个人信息编辑表单中使用
年龄计算: 根据出生日期计算年龄

## 自定义配置

BirthdayDatePicker组件可以像普通DatePicker组件一样进行配置
可以修改label、field、componentProps等所有属性
可以修改type为date仅选择日期，不包含时间
可以修改format和valueFormat调整日期格式
可以添加更多校验规则或事件处理函数

## 注意事项

BirthdayDatePicker是基于DatePicker组件的快捷组件，功能与DatePicker相同
预配置为日期时间选择，可根据需要修改为仅日期选择
建议根据实际业务场景修改field和label属性
