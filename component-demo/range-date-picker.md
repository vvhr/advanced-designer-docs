title: RangeDatePicker组件
description: RangeDatePicker范围日期选择快捷示例组件的用途和默认参数说明
keywords: RangeDatePicker,范围日期,快捷组件,示例组件
category: 组件菜单类

# RangeDatePicker组件

## 组件概述

RangeDatePicker是快捷示例组件，基于DatePicker组件封装，专门用于日期范围选择场景。已预配置日期范围相关的属性和校验规则。

## 组件类型

type: Inputer
component: DatePicker
menuRootKey: demo

## 默认参数

key: 空字符串（默认使用field值）
field: rangeDate
type: Inputer
label: 范围日期
hidden: false
value: []
component: DatePicker
componentProps:
  disabled: false
  editable: true
  clearable: false
  placeholder: null
  startPlaceholder: 开始时间
  endPlaceholder: 结束时间
  type: daterange
  format: YYYY-MM-DD
  valueFormat: YYYY-MM-DD HH:mm:ss
  rangeSeparator: -
componentEvent: 空对象
formItemProps:
  noLabel: false
  labelPosition: right
  subLabel: 空字符串
  autoRules: [isRequiredArray]
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

field: 默认为rangeDate，适合日期范围字段
label: 默认为范围日期，符合业务场景

### 日期类型

type: 预设置为daterange，使用日期范围选择
startPlaceholder: 预设置为开始时间
endPlaceholder: 预设置为结束时间
rangeSeparator: 预设置为-，分隔开始和结束日期

### 日期格式

format: 预设置为YYYY-MM-DD，显示格式
valueFormat: 预设置为YYYY-MM-DD HH:mm:ss，值格式

### 校验规则

autoRules: 预配置isRequiredArray（数组必填）规则
value: 预设置为空数组，存储开始和结束日期

### 组件属性

基于DatePicker组件，保持DatePicker的所有功能
可根据需要修改componentProps中的属性

## 使用场景

日期范围查询: 在查询表单中选择日期范围
时间段选择: 选择开始和结束时间段
报表筛选: 在报表筛选表单中使用

## 自定义配置

RangeDatePicker组件可以像普通DatePicker组件一样进行配置
可以修改label、field、componentProps等所有属性
可以修改type为datetimerange支持日期时间范围选择
可以修改format和valueFormat调整日期格式
可以添加更多校验规则或事件处理函数

## 注意事项

RangeDatePicker是基于DatePicker组件的快捷组件，功能与DatePicker相同
预配置为日期范围选择，value为数组类型
建议根据实际业务场景修改field和label属性
