title: CreditCodeInput 组件示例模板
description: CreditCodeInput信用代码输入快捷示例组件的用途和默认参数说明
keywords: CreditCodeInput,信用代码,快捷组件,示例组件
category: 示例模板类
---
# CreditCodeInput 信用代码输入框示例模板

## 模板用途
CreditCodeInput 并不是一个组件，而是针对信用代码输入场景的快捷示例，专门用于统一社会信用代码输入场景。
CreditCodeInput 由 Input 组件实现，支持 Input 组件的所有属性和配置能力。
已预配置信用代码相关的校验规则和属性，限制18位字符长度。
- **企业注册** - 在企业注册表单中快速添加信用代码输入框
- **企业信息** - 在企业信息编辑表单中使用
- **资质录入** - 在资质录入表单中使用

## 模板内容
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: 'creditCode',
  type: 'Inputer',
  label: '信用代码',
  hidden: false,
  value: '',
  component: 'Input',
  componentProps: {
    type: 'text',
    disabled: false,
    clearable: false,
    showPassword: false,
    showWordLimit: true,
    placeholder: null,
    maxlength: 18,
    minlength: null,
    readonly: false,
    autofocus: false,
    autocomplete: 'off',
    validateEvent: true,
    resize: 'none'
  },
  componentEvent: {},
  formItemProps: {
    noLabel: false,
    labelPosition: 'right',
    subLabel: '',
    autoRules: ['isRequired', 'isCreditCode']
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
