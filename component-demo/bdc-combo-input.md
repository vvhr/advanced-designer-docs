title: BdcComboInput组件
description: BdcComboInput不动产证号输入快捷示例组件的用途和默认参数说明
keywords: BdcComboInput,不动产证号,快捷组件,示例组件
category: 组件菜单类

# BdcComboInput组件

## 组件概述

BdcComboInput是快捷示例组件，基于ComboInput组件封装，专门用于不动产证号输入场景。已预配置复合输入模板和自定义校验规则。

## 组件类型

type: Inputer
component: ComboInput
menuRootKey: demo

## 默认参数

key: 空字符串（默认使用field值）
field: bdcNo
type: Inputer
label: 不动产证号
hidden: false
value: 空字符串
component: ComboInput
componentProps:
  template: [预配置的模板数组，包含年份选择器和编号输入框]
  disabled: false
componentEvent: 空对象
formItemProps:
  noLabel: false
  labelPosition: right
  subLabel: 空字符串
  _d_rules: [动态校验规则配置，使用IMMEDIATE_EXECUTE类型]
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

field: 默认为bdcNo，适合不动产证号字段
label: 默认为不动产证号，符合业务场景

### 复合输入模板

template: 预配置复合输入模板
包含固定文本鄂(、)宜昌市不动产权第、号
包含年份选择器，使用DatePicker组件，prop为year
包含编号输入框，使用Input组件，prop为no
最终组合格式为: 鄂(YYYY)宜昌市不动产权第XXXX号

### 校验规则

_d_rules: 预配置动态校验规则
使用IMMEDIATE_EXECUTE类型
通过正则表达式校验不动产证号格式
校验规则: /^鄂\\((\\d{4})\\)\\s*宜昌市不动产权第(\\d+)\\s*号$/

### 组件属性

基于ComboInput组件，保持ComboInput的所有功能
可根据需要修改componentProps中的属性

## 使用场景

不动产登记: 在不动产登记表单中使用
房产信息: 在房产信息表单中使用
证件录入: 在证件录入表单中使用

## 自定义配置

BdcComboInput组件可以像普通ComboInput组件一样进行配置
可以修改label、field、componentProps等所有属性
可以修改template数组调整输入模板结构
可以修改校验规则适配不同的证件格式
可以添加更多校验规则或事件处理函数

## 注意事项

BdcComboInput是基于ComboInput组件的快捷组件，功能与ComboInput相同
预配置的模板和校验规则针对宜昌市不动产证号格式
建议根据实际业务场景修改template和校验规则
template中的prop属性用于数据绑定，需与表单字段对应
