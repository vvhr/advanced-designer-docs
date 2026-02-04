title: AddressInput 组件示例模板
description: AddressInput地址输入快捷示例组件的用途和默认参数说明
keywords: AddressInput,地址输入,快捷组件,示例组件
category: 示例模板类
---
# AddressInput 地址输入框示例模板

## 模板用途
AddressInput 并不是一个组件，而是针对地址输入场景的快捷示例，专门用于地址输入场景。
AddressInput 由 Input 组件实现，支持 Input 组件的所有属性和配置能力。
已预配置地址相关的校验规则和属性，使用多行文本输入。
- **用户注册** - 在用户注册表单中快速添加地址输入框
- **收货地址** - 在收货地址表单中使用
- **联系地址** - 在联系地址表单中使用

## 模板内容
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: 'address',
  type: 'Inputer',
  label: '地址',
  hidden: false,
  value: '',
  component: 'Input',
  componentProps: {
    type: 'textarea',
    disabled: false,
    clearable: false,
    showPassword: false,
    showWordLimit: true,
    rows: 4,
    placeholder: null,
    maxlength: 200,
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
