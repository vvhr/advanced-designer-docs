title: BdcComboInput 组件示例模板
description: BdcComboInput不动产证号输入快捷示例组件的用途和默认参数说明
keywords: BdcComboInput,不动产证号,快捷组件,示例组件
category: 示例模板类
---
# BdcComboInput 不动产证号输入框示例模板

## 模板用途
BdcComboInput 并不是一个组件，而是针对不动产证号输入场景的快捷示例，专门用于不动产证号输入场景。
BdcComboInput 由 ComboInput 组件实现，支持 ComboInput 组件的所有属性和配置能力。
已预配置不动产证号的复合输入模板和校验规则，组合格式为：鄂(年份)宜昌市不动产权第编号号。
- **不动产登记** - 在不动产登记表单中快速添加证号输入框
- **房产信息** - 在房产信息表单中使用
- **证件录入** - 在证件录入表单中使用

## 模板内容
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: 'bdcNo',
  type: 'Inputer',
  label: '不动产证号',
  hidden: false,
  value: '',
  component: 'ComboInput',
  componentProps: {
    template: [
      { tag: 'span', content: '鄂(' },
      {
        tag: 'date-picker',
        prop: 'year',
        componentProps: {
          type: 'year',
          format: 'YYYY',
          valueFormat: 'YYYY',
          style: { width: '100px' },
          placeholder: '年份',
          prefixIcon: null
        }
      },
      { tag: 'span', content: ')宜昌市不动产权第' },
      {
        tag: 'input',
        prop: 'no',
        componentProps: {
          placeholder: '编号',
          style: { width: '100px' }
        }
      },
      { tag: 'span', content: '号' }
    ],
    disabled: false
  },
  componentEvent: {},
  formItemProps: {
    noLabel: false,
    labelPosition: 'right',
    subLabel: '',
    _d_rules: {
      enable: true,
      prop: 'rules',
      resolver: 'IMMEDIATE_EXECUTE',
      value: `{{return [
    {
      required: true,
      message: "请选择不动产权证的年份和编号",
      validator: (_rule, value) =>
        /^鄂\\((\\d{4})\\)\\s*宜昌市不动产权第(\\d+)\\s*号$/.test(String(value || "")),
    }
  ];
}}`
    }
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
