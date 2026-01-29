title: Upload组件
description: Upload文件上传器组件的用途、默认参数和可配置项说明
keywords: Upload,文件上传,上传组件,组件配置
category: 组件菜单类

# Upload组件

## 组件概述

Upload是输入型组件，用于文件上传功能。支持单文件和多文件上传，支持图片预览、文件列表展示等功能。

## 组件类型

type: Inputer
component: Upload
menuRootKey: inputer

## 默认参数

key: 空字符串（默认使用field值）
field: 空字符串（需手动设置）
type: Inputer
label: 新建文件上传器
hidden: false
value: []
component: Upload
componentProps:
  disabled: false
  style: 空对象
  fileKeys: {name: fileName, url: fileUrl}
  multiple: false
  accept: *
  limit: null
  sizeLimit: null
  listType: picture
  objectFit: fill
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
component: 组件名称（固定为Upload）
hidden: 是否隐藏组件

### 组件属性（componentProps）

value: 组件默认值（数组类型，存储文件对象）
disabled: 是否禁用
style: 自定义样式对象
fileKeys: 文件对象的键名映射，包含name和url字段
multiple: 是否多文件上传
accept: 接受的文件类型，如image/*、.pdf等
limit: 最大上传文件数量
sizeLimit: 单个文件大小限制（字节）
listType: 文件列表展示类型，可选值包括text、picture、picture-card
objectFit: 图片填充方式，可选值包括fill、contain、cover等

### 表单项属性（formItemProps）

noLabel: 是否不显示标签
labelPosition: 标签位置（left、right、top）
subLabel: 副标签文本
autoRules: 自动校验规则数组

### 布局属性（layoutProps）

span: 栅格占据的列数（1-24）
alone: 是否独占一行

## 事件配置

Upload组件支持以下事件：
change: 文件列表变化时触发
remove: 移除文件时触发
preview: 预览文件时触发
success: 上传成功时触发
error: 上传失败时触发

## 使用场景

图片上传: 上传头像、图片等
文件上传: 上传文档、附件等
批量上传: 多文件批量上传场景

## 注意事项

field属性是必填的，用于数据绑定
value为数组类型，存储文件对象数组
文件对象需包含name和url字段，可通过fileKeys配置键名映射
可通过accept限制上传文件类型，通过sizeLimit限制文件大小
