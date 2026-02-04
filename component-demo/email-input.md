title: EmailInput 组件示例模板
description: EmailInput邮箱输入快捷示例组件的用途和默认参数说明
keywords: EmailInput,邮箱,快捷组件,示例组件
category: 示例模板类
---
# EmailInput 邮箱输入框示例模板

## 模板用途
EmailInput 并不是一个组件，而是针对邮箱输入场景的快捷示例，专门用于邮箱地址输入场景。
EmailInput 由 Input 组件实现，支持 Input 组件的所有属性和配置能力。
已预配置邮箱相关的校验规则和属性，限制50位字符长度。
- **用户注册** - 在用户注册表单中快速添加邮箱输入框
- **联系方式** - 在联系方式表单中使用
- **账号绑定** - 在账号绑定表单中使用

## 模板内容
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: 'email',
  type: 'Inputer',
  label: '邮箱',
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
    maxlength: 50,
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
    autoRules: ['isRequired', 'isEmail']
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
