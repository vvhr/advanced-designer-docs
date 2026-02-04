title: ComboInput组件
description: ComboInput组合输入框组件的用途、默认参数和可配置项说明
keywords: ComboInput,组合输入框,输入型组件,组件配置
category: 组件菜单类
---
# ComboInput 组合输入框

## 组件用途
ComboInput是输入型组件，包含固定文本和可输入内容的自定义组合。
- **不动产证号** - 通过template配置组合内容,实现将固定文本+年份+编号进行组合并返回完整文本.
- **邮箱号** - 通过template配置组合内容,实现将邮箱前缀+邮箱后缀组合并返回完整邮箱号.


## 默认配置

```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: '',
  type: 'Inputer',
  label: '新建组合框',
  hidden: false,
  value: '',
  component: 'ComboInput',
  componentProps: {
    disabled: false,
    template: [
      { tag: 'span', content: '前缀' },
      {
        tag: 'input',
        prop: 'val1',
        componentProps: { placeholder: '变量1', style: { width: '100px' } }
      },
      { tag: 'span', content: '中间' },
      {
        tag: 'input',
        prop: 'val2',
        componentProps: { placeholder: '变量2', style: { width: '100px' } }
      },
      { tag: 'span', content: '后缀' }
    ] as ComboTemplate[]
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
