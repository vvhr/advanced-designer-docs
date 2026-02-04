title: RangeDatePicker 组件示例模板
description: RangeDatePicker范围日期选择快捷示例组件的用途和默认参数说明
keywords: RangeDatePicker,范围日期,快捷组件,示例组件
category: 示例模板类
---
# RangeDatePicker 范围日期选择器示例模板

## 模板用途
RangeDatePicker 并不是一个组件，而是针对日期范围选择场景的快捷示例，专门用于日期范围选择场景。
RangeDatePicker 由 DatePicker 组件实现，支持 DatePicker 组件的所有属性和配置能力。
已预配置日期范围相关的属性和数组必填校验规则。
- **日期范围查询** - 在查询表单中选择日期范围
- **时间段选择** - 选择开始和结束时间段
- **报表筛选** - 在报表筛选表单中使用

## 模板内容
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: 'rangeDate',
  type: 'Inputer',
  label: '范围日期',
  hidden: false,
  value: [],
  component: 'DatePicker',
  componentProps: {
    disabled: false,
    editable: true,
    clearable: false,
    placeholder: null,
    startPlaceholder: '开始时间',
    endPlaceholder: '结束时间',
    type: 'daterange',
    format: 'YYYY-MM-DD',
    valueFormat: 'YYYY-MM-DD HH:mm:ss',
    rangeSeparator: '-'
  },
  componentEvent: {},
  formItemProps: {
    noLabel: false,
    labelPosition: 'right',
    subLabel: '',
    autoRules: ['isRequiredArray']
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
