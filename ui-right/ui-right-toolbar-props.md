title: 右侧工具栏-属性
description: 右侧工具栏属性面板的功能说明
keywords: 属性面板,组件属性,配置项,属性编辑
category: UI类
---

## 面板说明

属性面板用于配置选中组件的基本属性，包括组件属性、表单项属性、布局属性等。面板在选中组件时自动显示，未选中组件时显示提示信息。

## 配置分类

**基本属性**
- `key` - 组件的唯一标识符
- `field` - 表单字段名，用于数据绑定
- `type` - 组件类型（Decorator、Inputer、Container等）
- `component` - 组件名称（Input、Select、Alert等）
- `label` - 组件标签文本
- `hidden` - 是否隐藏组件

**组件属性（componentProps）**
- 组件特有的属性配置，不同组件有不同的属性项
- 例如: Input组件的placeholder、maxlength、clearable等
- 例如: Select组件的options、multiple、filterable等

**表单项属性（formItemProps）**
- 表单表单项的配置属性
- `noLabel` - 是否不显示标签
- `labelPosition` - 标签位置（left、right、top）
- `subLabel` - 副标签文本
- `autoRules` - 自动校验规则数组

**布局属性（layoutProps）**
- 组件在表单中的布局配置
- `span` - 栅格占据的列数（1-24）
- `alone` - 是否独占一行

**外部属性（outsideProps）**
- 组件外层的包装配置
- `enable` - 是否启用外层包装
- `direction` - 包装方向（row、column）
- `style` - 自定义样式对象

## 动态属性配置

属性面板支持通过ResolverValue机制配置动态属性，使用_d_前缀的属性可实现动态值绑定。支持四种解析类型: FORM_SCHEMA_FN、COMPONENT_EVENT_FN、IMMEDIATE_EXECUTE、FORM_SCHEMA_DOM_FN。

## 使用场景

- **组件配置** - 配置组件的基本属性和行为
- **样式调整** - 调整组件的布局和样式
- **动态绑定** - 配置动态属性，实现灵活的表单逻辑
