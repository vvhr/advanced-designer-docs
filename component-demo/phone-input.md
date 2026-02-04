title: PhoneInput 组件示例模板
description: PhoneInput手机号码输入快捷示例组件的用途和默认参数说明
keywords: PhoneInput,手机号输入,快捷组件,示例组件
category: 示例模板类
---
# PhoneInput 手机号码输入框示例模板

## 模板用途
PhoneInput 并不是一个组件，而是针对手机号码输入场景的快捷示例，专门用于手机号码输入场景。
PhoneInput 由 Input 组件实现，支持 Input 组件的所有属性和配置能力。
已预配置手机号相关的校验规则和属性，限制11位字符长度。
- **用户注册** - 在用户注册表单中快速添加手机号输入框
- **联系方式** - 在联系方式表单中使用
- **短信验证** - 在短信验证码表单中使用

## 模板内容
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: 'phone',
  type: 'Inputer',
  label: '手机号码',
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
    maxlength: 11,
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
    autoRules: ['isRequired', 'isMobilePhone']
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
