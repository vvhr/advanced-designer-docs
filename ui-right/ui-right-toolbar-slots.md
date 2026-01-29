title: 右侧工具栏-插槽
description: 右侧工具栏插槽面板的功能说明
keywords: 插槽面板,插槽配置,自定义内容,渲染函数
category: UI类

# 右侧工具栏-插槽

## 面板说明

插槽面板用于自定义选中组件的插槽内容，实现个性化展示。支持通过RenderDesigner可视化编辑器或代码编辑器配置插槽内容。

## 功能特性

### 插槽列表

展示方式: 列出组件支持的所有插槽
插槽类型: 不同组件支持不同的插槽
例如: Input组件支持prefix、suffix、prepend、append等插槽
例如: Select组件支持prefix、empty等插槽

### 插槽编辑

编辑方式: 通过RenderDesigner可视化编辑器或代码编辑器编辑插槽内容
渲染类型: 支持VNode渲染函数
函数签名: 函数接收excontext上下文对象，返回VNode

### 函数类型

FORM_SCHEMA_DOM_FN: DOM渲染函数类型
参数: (excontext: Recordable) => VNode
用途: 返回VNode用于插槽渲染

## 使用场景

自定义图标: 在输入框前后添加自定义图标
自定义内容: 在组件中插入自定义HTML内容
复杂布局: 通过插槽实现复杂的组件布局

## 注意事项

插槽内容通过VNode渲染，需要了解Vue的渲染机制
建议使用RenderDesigner可视化编辑器，降低使用门槛
插槽函数中可通过excontext访问上下文对象
