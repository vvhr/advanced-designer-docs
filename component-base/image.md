title: Image组件
description: Image静态图片组件的用途、默认参数和可配置项说明
keywords: Image,图片组件,装饰型组件,组件配置
category: 组件菜单类

# Image组件

## 组件概述

Image是装饰型组件，用于在表单中展示图片。支持懒加载、预览等功能。不参与表单数据收集，仅用于展示和装饰。

## 组件类型

type: Decorator
component: Image
menuRootKey: decorator

## 默认参数

key: 空字符串（需手动设置）
field: 空字符串（装饰型组件不需要）
type: Decorator
label: 新建静态图片
hidden: false
component: Image
componentProps:
  src: 空字符串
  fit: fill
  lazy: false
  alt: 空字符串
  loading: lazy
  hideOnClickModal: false
  previewSrcList: []
  zIndex: 2000
  initialIndex: 0
  closeOnPressEscape: true
  previewTeleported: false
  infinite: true
  zoomRate: 1.2
  minScale: 0.2
  maxScale: 7
  showProgress: false
layoutProps:
  span: 12
  alone: false

## 可配置项

### 基本属性

key: 组件唯一标识符
type: 组件类型（固定为Decorator）
component: 组件名称（固定为Image）
hidden: 是否隐藏组件

### 组件属性（componentProps）

src: 图片地址URL
fit: 图片填充方式，可选值包括fill、contain、cover、none、scale-down
lazy: 是否懒加载
alt: 图片描述文本
loading: 加载方式，可选值包括lazy、eager
hideOnClickModal: 点击遮罩层是否关闭预览
previewSrcList: 预览图片列表数组
zIndex: 预览时的层级
initialIndex: 预览时的初始索引
closeOnPressEscape: 按ESC键是否关闭预览
previewTeleported: 预览是否传送到body
infinite: 预览时是否无限循环
zoomRate: 预览时的缩放比例
minScale: 预览时的最小缩放比例
maxScale: 预览时的最大缩放比例
showProgress: 预览时是否显示进度条

### 布局属性（layoutProps）

span: 栅格占据的列数（1-24）
alone: 是否独占一行

## 使用场景

图片展示: 在表单中展示产品图片、头像等
图片预览: 点击图片可预览大图
图片说明: 配合文字说明展示图片内容

## 注意事项

Image是装饰型组件，不参与表单数据收集
组件没有field属性，不需要绑定表单数据
可通过previewSrcList配置预览图片列表
支持懒加载，提升页面性能
