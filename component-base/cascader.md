title: Cascader组件
description: Cascader级联选择框组件的用途、默认参数和可配置项说明
keywords: Cascader,级联选择,级联选择框,组件配置
category: 组件菜单类
---
# Cascader 级联选择器

## 组件概述
Cascader是输入型组件，用于级联选择。支持多级选项的级联选择，常用于地区选择、分类选择等场景。
- **地区选择** - 选择省市区等地区信息
- **分类选择** - 选择多级分类
- **层级数据** - 选择具有层级关系的数据

## 默认配置

```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: '',
  type: 'Inputer',
  component: 'Cascader',
  label: '新建级联选择',
  hidden: false,
  componentProps: {
    options: [
      {
        value: '1',
        label: '选项1',
        children: [
          { value: '1-1', label: '选项1-1' },
          { value: '1-2', label: '选项1-2' }
        ]
      },
      {
        value: '2',
        label: '选项2',
        children: [
          { value: '2-1', label: '选项2-1' },
          { value: '2-2', label: '选项2-2' }
        ]
      }
    ],
    props: {
      expandTrigger: 'click',
      multiple: false,
      checkStrictly: false,
      emitPath: true
    },
    placeholder: null,
    disabled: false,
    clearable: false,
    showAllLevels: false,
    collapseTags: false,
    collapseTagsTooltip: false,
    maxCollapseTagsTooltipHeight: null,
    separator: ' / ',
    style: {},
    effect: 'light',
    tagType: 'primary',
    tagEffect: 'plain',
    validateEvent: true,
    maxCollapseTags: 1,
    placement: 'bottom-start',
    showCheckedStrategy: 'child'
  },
  componentEvent: {},
  formItemProps: {
    noLabel: false,
    labelPosition: 'right',
    subLabel: '',
    autoRules: []
  },
  layoutProps: {
    span: 12,
    alone: false
  },
  insideProps: {},
  outsideProps: {
    enable: false,
    direction: 'row',
    style: {}
  }
}
```

## 可配置属性

**基本属性**
- key: 组件唯一标识符（默认使用field值）
- field: 表单字段名，用于数据绑定（必填）
- type: 组件类型（固定为Inputer）
- component: 组件名称（固定为Cascader）
- hidden: 是否隐藏组件

**组件属性（componentProps）**
- options: 级联选项数组，支持多级嵌套结构
- props: 级联选择器的配置对象
- expandTrigger: 展开触发方式，可选值包括click、hover
- multiple: 是否多选
- checkStrictly: 是否严格的遵守父子节点不关联
- emitPath: 在选中节点改变时，是否返回由该节点所在的各级菜单的值所组成的数组
- placeholder: 输入框占位符
- disabled: 是否禁用
- clearable: 是否显示清除按钮
- showAllLevels: 输入框中是否显示选中值的完整路径
- collapseTags: 多选模式下是否折叠标签
- collapseTagsTooltip: 当鼠标悬停于折叠标签时，是否显示所有选中的标签
- maxCollapseTagsTooltipHeight: 折叠标签提示的最大高度
- separator: 选项分隔符
- style: 自定义样式对象
- effect: 主题样式，可选值包括light、dark
- tagType: 标签类型，可选值包括success、info、warning、danger、primary
- tagEffect: 标签效果，可选值包括dark、light、plain
- validateEvent: 是否触发表单校验
- maxCollapseTags: 多选模式下最多显示的标签数量
- placement: 弹出框位置
- showCheckedStrategy: 多选模式下显示选中节点的策略

**表单项属性（formItemProps）**
- noLabel: 是否不显示标签
- labelPosition: 标签位置（left、right、top）
- subLabel: 副标签文本
- autoRules: 自动校验规则数组

**布局属性（layoutProps）**
- span: 栅格占据的列数（1-24）
- alone: 是否独占一行

## 事件配置
Cascader组件支持以下事件：
* _d_onChange: 选中值变化时触发
* _d_onBlur: 失去焦点时触发
* _d_onFocus: 获得焦点时触发
* _d_onClear: 清空时触发


