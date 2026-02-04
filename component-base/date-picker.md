title: DatePicker组件
description: DatePicker日期时间选择器组件的用途、默认参数和可配置项说明
keywords: DatePicker,日期时间选择器,输入型组件,组件配置
category: 组件菜单类
---
# DatePicker 日期时间选择器

## 组件用途
DatePicker 是输入型组件，用于选择日期或日期时间。支持多种选择模式，包括单选、多选、范围选择等。
- **日期选择** - 选择单个日期或日期范围
- **日期时间选择** - 选择包含时间的日期
- **月份/年份选择** - 选择月份或年份
- **周选择** - 选择周

## 默认配置
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: '',
  type: 'Inputer',
  label: '新建日期时间选择框',
  hidden: false,
  value: null,
  component: 'DatePicker',
  componentProps: {
    disabled: false,
    editable: true,
    clearable: false,
    placeholder: null,
    startPlaceholder: '开始时间',
    endPlaceholder: '结束时间',
    type: 'datetime',
    format: 'YYYY-MM-DD',
    valueFormat: 'YYYY-MM-DD HH:mm:ss',
    rangeSeparator: '-'
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

## 可配置属性

**基本属性**
- `key` - 组件唯一标识符
- `field` - 字段名称，用于表单数据绑定
- `type` - 组件类型（固定为Inputer）
- `component` - 组件名称（固定为DatePicker）
- `label` - 字段标签文本
- `_d_label` - 动态标签配置（ResolverValue类型）
- `hidden` - 是否隐藏组件
- `_d_hidden` - 动态隐藏配置（ResolverValue类型）
- `value` - 默认值（单选时为字符串或null，多选/范围选择时为数组）
- `_d_value` - 动态默认值配置（ResolverValue类型）

**组件属性 (componentProps)**
- `disabled` - 是否禁用
- `_d_disabled` - 动态禁用配置（ResolverValue类型）
- `clearable` - 是否显示清除按钮
- `type` - 时间类型，可选值:
  - `date` - 日期
  - `dates` - 日期(多选)
  - `daterange` - 日期(范围)
  - `datetime` - 日期时间
  - `datetimerange` - 日期时间(范围)
  - `month` - 月份
  - `months` - 月份(多选)
  - `monthrange` - 月份(范围)
  - `year` - 年
  - `years` - 年(多选)
  - `yearrange` - 年(范围)
  - `week` - 周
- `placeholder` - 占位文本（非范围选择时显示）
- `startPlaceholder` - 开始时间占位文本（范围选择时显示）
- `endPlaceholder` - 结束时间占位文本（范围选择时显示）
- `rangeSeparator` - 范围分隔符（范围选择时显示）
- `format` - 显示格式（与取值无关，仅供展示给用户的格式）
- `valueFormat` - 取值格式（根据业务需求选择所需的取值格式）
- `_d_defaultTime` - 默认时刻配置（范围选择时选中日期所使用的当日内具体时刻，ResolverValue类型）
- `_d_disabledDate` - 禁止日期配置（返回闭包函数判断日期是否被禁用，ResolverValue类型）
- `unlinkPanels` - 在范围选择器里取消两个日期面板之间的联动
- `validateEvent` - 输入时是否触发表单验证
- `placement` - 下拉框出现的位置
- `style` - 自定义样式对象

**标题属性 (formItemProps)**
- `noLabel` - 是否不显示标签
- `labelPosition` - 标签位置（left、right、top）
- `labelWidth` - 标签宽度
- `labelMaxWidth` - 标签最大宽度
- `subLabel` - 副标签文本
- `autoRules` - 自动校验规则
- `_d_rules` - 动态校验规则配置（ResolverValue类型）

**布局属性 (layoutProps)**
- `span` - 栅格占据的列数（1-24）
- `alone` - 是否独占一行
- `colStyle` - 列自定义样式对象

**外部属性 (outsideProps)**
- `enable` - 是否启用外层包装
- `direction` - 包装方向（row、column）
- `style` - 自定义样式对象

**组件事件 (componentEvent)**
- `_d_onChange` - 值改变时触发的回调函数（ResolverValue类型）
  - 参数: `event`（组件新的值）, `formModel`, `column`, `disabled`, `excontext`
  - 返回值: 无需返回
