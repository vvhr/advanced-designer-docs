title: NameInput 组件示例模板
description: NameInput姓名输入快捷示例组件的用途和默认参数说明
keywords: NameInput,姓名输入,快捷组件,示例组件
category: 示例模板类
---
# NameInput 姓名输入框示例模板

## 模板用途
NameInput 并不是一个组件，而是针对姓名输入场景的快捷示例，专门用于姓名输入场景。
NameInput 由 Input 组件实现，支持 Input 组件的所有属性和配置能力。
已预配置姓名相关的校验规则和属性，限制20位字符长度，不允许空格。
- **用户注册** - 在用户注册表单中快速添加姓名输入框
- **个人信息** - 在个人信息编辑表单中使用
- **表单模板** - 作为表单模板的快速组件

## 模板内容
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: 'name',
  type: 'Inputer',
  label: '姓名',
  hidden: false,
  value: '',
  component: 'Input',
  componentProps: {
    type: 'text',
    disabled: false,
    clearable: false,
    showPassword: false,
    showWordLimit: false,
    placeholder: null,
    maxlength: 20,
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
    autoRules: ['isRequired', 'noSpace']
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
