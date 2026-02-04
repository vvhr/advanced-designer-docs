title: BirthdayDatePicker 组件示例模板
description: BirthdayDatePicker出生日期选择快捷示例组件的用途和默认参数说明
keywords: BirthdayDatePicker,出生日期,快捷组件,示例组件
category: 示例模板类
---
# BirthdayDatePicker 出生日期选择器示例模板

## 模板用途
BirthdayDatePicker 并不是一个组件，而是针对出生日期选择场景的快捷示例，专门用于出生日期选择场景。
BirthdayDatePicker 由 DatePicker 组件实现，支持 DatePicker 组件的所有属性和配置能力。
已预配置出生日期相关的属性和必填校验规则。
- **用户注册** - 在用户注册表单中快速添加出生日期选择
- **个人信息** - 在个人信息编辑表单中使用
- **年龄计算** - 根据出生日期计算年龄

## 模板内容
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: 'birthday',
  type: 'Inputer',
  label: '出生日期',
  hidden: false,
  value: null,
  component: 'DatePicker',
  componentProps: {
    disabled: false,
    editable: true,
    clearable: false,
    placeholder: null,
    startPlaceholder: '开始时间',
    endPlaceholder: '结束时间',
    type: 'datetime',
    format: 'YYYY-MM-DD',
    valueFormat: 'YYYY-MM-DD HH:mm:ss',
    rangeSeparator: '-'
  },
  componentEvent: {},
  formItemProps: {
    noLabel: false,
    labelPosition: 'right',
    subLabel: '',
    autoRules: ['isRequired']
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
