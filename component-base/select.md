title: Select组件
description: Select下拉选择框组件的用途、默认参数和可配置项说明
keywords: Select,下拉选择框,输入型组件,组件配置
category: 组件菜单类
---
# Select 下拉选择框

## 组件用途
Select 是输入型组件，用于从下拉列表中选择一个或多个选项。支持单选、多选、搜索、创建新条目等功能。
- **单选场景** - 从多个选项中选择一个值
- **多选场景** - 从多个选项中选择多个值
- **可搜索选择** - 支持搜索过滤选项

## 默认配置
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: '',
  type: 'Inputer',
  label: '新建下拉选择框',
  hidden: false,
  value: null,
  component: 'Select',
  componentProps: {
    disabled: false,
    clearable: false,
    placeholder: null,
    multiple: false,
    collapseTags: false,
    collapseTagsTooltip: false,
    multipleLimit: 0,
    autocomplete: 'off',
    filterable: false,
    allowCreate: false,
    noMatchText: '无匹配数据',
    noDataText: '无数据',
    reserveKeyword: true,
    defaultFirstOption: false,
    popperAppendToBody: true,
    automaticDropdown: false,
    options: [
      { label: '选项1', value: '1', disabled: false },
      { label: '选项2', value: '2', disabled: false },
      { label: '选项3', value: '3', disabled: false }
    ]
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
- `key` - 组件唯一标识符
- `field` - 字段名称，用于表单数据绑定
- `type` - 组件类型（固定为Inputer）
- `component` - 组件名称（固定为Select）
- `label` - 字段标签文本
- `_d_label` - 动态标签配置（ResolverValue类型）
- `hidden` - 是否隐藏组件
- `_d_hidden` - 动态隐藏配置（ResolverValue类型）
- `value` - 默认值（单选时为字符串或null，多选时为数组）
- `_d_value` - 动态默认值配置（ResolverValue类型）

**组件属性 (componentProps)**
- `disabled` - 是否禁用
- `_d_disabled` - 动态禁用配置（ResolverValue类型）
- `clearable` - 是否显示清除按钮
- `placeholder` - 占位文本
- `placement` - 下拉框出现的位置
- `options` - 下拉选择框的选项列表
- `_d_options` - 动态选项配置（函数编程动态返回下拉选择框的选项列表，ResolverValue类型）
- `multiple` - 是否多选
- `collapseTags` - 多选时是否将选中值按文字的形式展示
- `collapseTagsTooltip` - 当鼠标悬停于折叠标签的文本时，是否显示所有选中的标签
- `multipleLimit` - 多选时用户最多可以选择的项目数，为 0 则不限制
- `filterable` - 是否可搜索
- `allowCreate` - 是否允许用户创建新条目，需配合 filterable 使用
- `noMatchText` - 搜索条件无匹配时显示的文字
- `noDataText` - 选项为空时显示的文字
- `reserveKeyword` - 多选且可搜索时，是否在选中一个选项后保留当前的搜索关键词
- `defaultFirstOption` - 在输入框按下回车，选择第一个匹配项
- `style` - 自定义样式对象

**标题属性 (formItemProps)**
- `noLabel` - 是否不显示标签
- `labelPosition` - 标签位置（left、right、top）
- `labelWidth` - 标签宽度
- `labelMaxWidth` - 标签最大宽度
- `subLabel` - 副标签文本
- `autoRules` - 自动校验规则
- `_d_rules` - 动态校验规则配置（ResolverValue类型）

**布局属性 (layoutProps)**
- `span` - 栅格占据的列数（1-24）
- `alone` - 是否独占一行
- `colStyle` - 列自定义样式对象

**外部属性 (outsideProps)**
- `enable` - 是否启用外层包装
- `direction` - 包装方向（row、column）
- `style` - 自定义样式对象

**组件事件 (componentEvent)**
- `_d_onChange` - 值改变时触发的回调函数（ResolverValue类型）
- `_d_onVisibleChange` - 下拉框出现/隐藏时触发的回调函数（ResolverValue类型）
- `_d_onRemoveTag` - 多选模式下移除tag时触发的回调函数（ResolverValue类型）
- `_d_onClear` - 点击清除按钮时触发的回调函数（ResolverValue类型）
- `_d_onBlur` - 失去焦点时触发的回调函数（ResolverValue类型）
- `_d_onFocus` - 获得焦点时触发的回调函数（ResolverValue类型）
