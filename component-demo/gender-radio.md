title: GenderRadio 组件示例模板
description: GenderRadio性别单选快捷示例组件的用途和默认参数说明
keywords: GenderRadio,性别,快捷组件,示例组件
category: 示例模板类
---
# GenderRadio 性别单选框示例模板

## 模板用途
GenderRadio 并不是一个组件，而是针对性别选择场景的快捷示例，专门用于性别选择场景。
GenderRadio 由 Radio 组件实现，支持 Radio 组件的所有属性和配置能力。
已预配置性别选项（男、女）和必填校验规则。
- **用户注册** - 在用户注册表单中快速添加性别选择
- **个人信息** - 在个人信息编辑表单中使用
- **实名认证** - 在实名认证表单中使用

## 模板内容
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: 'gender',
  type: 'Inputer',
  label: '性别',
  hidden: false,
  value: '',
  component: 'Radio',
  componentProps: {
    disabled: false,
    clearable: false,
    options: [
      { value: '1', label: '男', disabled: false, border: true },
      { value: '2', label: '女', disabled: false, border: true }
    ],
    optionKeys: {
      label: 'label',
      value: 'value',
      children: 'children',
      disabled: 'disabled'
    },
    style: {}
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
