title: Select组件
description: Select下拉选择框组件的用途、默认参数和可配置项说明
keywords: Select,下拉选择框,选择组件,组件配置
category: 组件菜单类

# Select组件

## 组件概述

Select是输入型组件，用于从多个选项中选择一个或多个值。当选项过多时，使用下拉菜单展示并选择内容。

## 组件类型

type: Inputer
component: Select
menuRootKey: inputer

## 默认参数

key: 空字符串（默认使用field值）
field: 空字符串（需手动设置）
type: Inputer
label: 新建下拉选择框
hidden: false
value: null
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
  options: [{label: 选项1, value: 1}, {label: 选项2, value: 2}, {label: 选项3, value: 3}]
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
component: 组件名称（固定为Select）
hidden: 是否隐藏组件

### 组件属性（componentProps）

value: 组件默认值（单选为null，多选为[]）
disabled: 是否禁用
clearable: 是否显示清除按钮
placeholder: 选择框占位符文本
multiple: 是否多选
collapseTags: 多选时是否将选中值按文字的形式展示
collapseTagsTooltip: 当鼠标悬停于折叠标签时，是否显示所有选中的标签
multipleLimit: 多选时用户最多可以选择的项目数，为0则不限制
autocomplete: 自动完成属性
filterable: 是否可搜索
allowCreate: 是否允许用户创建新条目
noMatchText: 搜索条件无匹配时显示的文字
noDataText: 选项为空时显示的文字
reserveKeyword: 多选且可搜索时，是否在选中一个选项后保留当前的搜索关键词
defaultFirstOption: 在输入框按下回车，选择第一个匹配项
popperAppendToBody: 是否将弹出框插入至body元素
automaticDropdown: 对于不可搜索的Select，是否在输入框获得焦点后自动弹出选项菜单
options: 选项数据数组，每个选项包含label、value、disabled等属性

### 表单项属性（formItemProps）

noLabel: 是否不显示标签
labelPosition: 标签位置（left、right、top）
subLabel: 副标签文本
autoRules: 自动校验规则数组

### 布局属性（layoutProps）

span: 栅格占据的列数（1-24）
alone: 是否独占一行

## 事件配置

Select组件支持以下事件：
change: 选中值发生变化时触发
visible-change: 下拉框出现/隐藏时触发
remove-tag: 多选模式下移除tag时触发
clear: 可清空的单选模式下用户点击清空按钮时触发
blur: 当选择器的输入框失去焦点时触发
focus: 当选择器的输入框获得焦点时触发

## 插槽配置

Select组件支持以下插槽：
prefix: 选择框头部内容
empty: 无选项时的列表内容

## 使用场景

单选场景: 从多个选项中选择一个值，如性别、状态等
多选场景: 从多个选项中选择多个值，如标签、分类等
搜索选择: 选项较多时，通过搜索快速定位选项
动态选项: 选项数据来自API或上下文对象

## 注意事项

field属性是必填的，用于数据绑定
单选模式下value为null，多选模式下value为数组
options数组中的value值类型需与表单数据类型一致
可通过filterable实现搜索功能，提升用户体验
