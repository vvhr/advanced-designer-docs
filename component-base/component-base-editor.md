title: Editor组件
description: Editor富文本输入框组件的用途、默认参数和可配置项说明
keywords: Editor,富文本,文本编辑器,组件配置
category: 组件菜单类

# Editor组件

## 组件概述

Editor是输入型组件，提供富文本编辑功能。支持格式化文本、插入图片、表格等功能，用于输入富文本内容。

## 组件类型

type: Inputer
component: Editor
menuRootKey: inputer

## 默认参数

key: 空字符串（默认使用field值）
field: 空字符串（需手动设置）
type: Inputer
label: 新建富文本框
hidden: false
value: null
component: Editor
componentProps:
  disabled: false
  placeholder: null
  editorHeight: 200
  viewHeight: 200
  mode: simple
  toolbarKeys: []
  toolbarExcludeKeys: []
  addToolbarKeys: []
  theme: light
  contentIsMarkdown: false
  contentRetention: false
  contentRetentionKey: 空字符串
  resizable: false
  toolbarTipEnable: false
  lang: zh-CN
  editorOptions: 空对象
  style: 空对象
  freshKey: 0
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
component: 组件名称（固定为Editor）
hidden: 是否隐藏组件

### 组件属性（componentProps）

value: 组件默认值（字符串类型，HTML或Markdown格式）
disabled: 是否禁用
placeholder: 编辑器占位符
editorHeight: 编辑器高度（像素）
viewHeight: 预览高度（像素）
mode: 编辑器模式，可选值包括simple、default等
toolbarKeys: 工具栏按钮数组
toolbarExcludeKeys: 排除的工具栏按钮数组
addToolbarKeys: 额外添加的工具栏按钮数组
theme: 主题，可选值包括light、dark
contentIsMarkdown: 内容是否为Markdown格式
contentRetention: 是否保留内容
contentRetentionKey: 内容保留的键名
resizable: 是否可调整大小
toolbarTipEnable: 是否启用工具栏提示
lang: 语言，默认zh-CN
editorOptions: 编辑器选项对象
style: 自定义样式对象
freshKey: 刷新键，用于强制刷新编辑器

### 表单项属性（formItemProps）

noLabel: 是否不显示标签
labelPosition: 标签位置（left、right、top）
subLabel: 副标签文本
autoRules: 自动校验规则数组

### 布局属性（layoutProps）

span: 栅格占据的列数（1-24）
alone: 是否独占一行

## 事件配置

Editor组件支持以下事件：
change: 内容改变时触发
blur: 失去焦点时触发
focus: 获得焦点时触发

## 使用场景

富文本编辑: 编辑带格式的文本内容
内容发布: 发布文章、公告等富文本内容
文档编辑: 编辑文档、说明等

## 注意事项

field属性是必填的，用于数据绑定
value为字符串类型，可以是HTML或Markdown格式
可通过toolbarKeys配置工具栏按钮
可通过mode配置编辑器模式
支持Markdown格式的内容编辑
