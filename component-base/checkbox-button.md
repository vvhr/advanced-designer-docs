title: CheckboxButton组件
description: CheckboxButton复选按钮组组件的用途、默认参数和可配置项说明
keywords: CheckboxButton,复选按钮,复选框组,组件配置
category: 组件菜单类
---
# CheckboxButton 多选按钮组

## 组件用途
CheckboxButton是输入型组件，用于多选场景。通过按钮组的形式展示选项，支持多个选项的选择。
- **多选场景** - 从多个选项中选择多个值
- **标签选择** - 选择多个标签
- **分类选择** - 选择多个分类

## 默认配置

```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: '',
  type: 'Inputer',
  component: 'CheckboxButton',
  label: '新复选按钮',
  hidden: false,
  value: [],
  componentProps: {
    options: [
      { value: '1', label: '选项1', disabled: false },
      { value: '2', label: '选项2', disabled: false }
    ],
    disabled: false,
    style: {},
    textColor: '#ffffff',
    fill: '#409EFF',
    tag: 'div',
    validateEvent: true
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
  outsideProps: {}
}
```

## 可配置属性

**基本属性**
- key: 组件唯一标识符（默认使用field值）
- field: 表单字段名，用于数据绑定（必填）
- type: 组件类型（固定为Inputer）
- component: 组件名称（固定为CheckboxButton）
- hidden: 是否隐藏组件

**组件属性（componentProps）**
- value: 组件默认值（数组类型，存储选中项的value数组）
- options: 选项数组，每个选项包含value、label、disabled属性
- disabled: 是否禁用整个组件
- style: 自定义样式对象
- textColor: 选中时的文字颜色
- fill: 选中时的填充颜色
- tag: 根元素标签，默认div
- validateEvent: 是否触发表单校验

**表单项属性（formItemProps）**
- noLabel: 是否不显示标签
- labelPosition: 标签位置（left、right、top）
- subLabel: 副标签文本
- autoRules: 自动校验规则数组

**布局属性（layoutProps）**
- span: 栅格占据的列数（1-24）
- alone: 是否独占一行

## 事件配置
CheckboxButton组件支持以下事件：

* _d_onChange: 选中值变化时触发
