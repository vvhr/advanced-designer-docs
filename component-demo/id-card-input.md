title: IdCardInput 组件示例模板
description: IdCardInput身份证号码输入快捷示例组件的用途和默认参数说明
keywords: IdCardInput,身份证输入,快捷组件,示例组件
category: 示例模板类
---
# IdCardInput 身份证号码输入框示例模板

## 模板用途
IdCardInput 并不是一个组件，而是针对身份证号码输入场景的快捷示例，专门用于身份证号码输入场景。
IdCardInput 由 Input 组件实现，支持 Input 组件的所有属性和配置能力。
已预配置身份证相关的校验规则和属性，限制18位字符长度。
- **用户注册** - 在用户注册表单中快速添加身份证输入框
- **实名认证** - 在实名认证表单中使用
- **个人信息** - 在个人信息编辑表单中使用

## 模板内容
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: 'idCard',
  type: 'Inputer',
  label: '身份证号码',
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
    autoRules: ['isRequired', 'isIdCard']
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
