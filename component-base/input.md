title: Input组件
description: Input输入框组件的用途、默认参数和可配置项说明
keywords: Input,输入框,输入型组件,组件配置
category: 组件菜单类
---
# Input 输入框

## 组件用途
Input 是输入型组件，用于通过鼠标或键盘输入字符。支持文本、多行文本、密码等多种输入类型。
- **文本输入** - 输入用户名、姓名等文本信息
- **多行文本** - 输入备注、描述等多行文本
- **密码输入** - 输入密码等敏感信息

## 默认配置
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: '',
  type: 'Inputer',
  label: '新建输入框',
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
    maxlength: null,
    minlength: null,
    readonly: false,
    autofocus: false,
    validateEvent: true,
    resize: 'none'
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
- `component` - 组件名称（固定为Input）
- `label` - 字段标签文本
- `_d_label` - 动态标签配置（ResolverValue类型）
- `hidden` - 是否隐藏组件
- `_d_hidden` - 动态隐藏配置（ResolverValue类型）
- `value` - 默认值
- `_d_value` - 动态默认值配置（ResolverValue类型）

**组件属性 (componentProps)**
- `disabled` - 是否禁用
- `_d_disabled` - 动态禁用配置（ResolverValue类型）
- `clearable` - 是否显示清除按钮
- `placeholder` - 占位文本
- `type` - 输入框类型，可选值: text（文本）、textarea（多行文本）、password（密码）
- `showPassword` - 是否显示切换密码可见性的按钮（仅当 type 为 password 时有效）
- `showWordLimit` - 是否显示字数统计（必须设置最大长度才能正常显示）
- `maxlength` - 最大长度（最多可输入字数）
- `minlength` - 最小长度（最少可输入字数）
- `readonly` - 是否只读
- `autofocus` - 是否自动聚焦
- `resize` - 调整大小，可选值: none（不可调整）、both（双向调整）、horizontal（水平调整）、vertical（垂直调整）（仅当 type 为 textarea 时有效）
- `rows` - 输入框行数（仅当 type 为 textarea 时有效）
- `validateEvent` - 输入时是否触发表单验证
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
- `_d_onBlur` - 失去焦点时触发的回调函数（ResolverValue类型）
  - 参数: `event`, `formModel`, `column`, `disabled`, `excontext`
  - 返回值: 无需返回
- `_d_onFocus` - 获得焦点时触发的回调函数（ResolverValue类型）
  - 参数: `event`, `formModel`, `column`, `disabled`, `excontext`
  - 返回值: 无需返回
- `_d_onChange` - 值改变时触发的回调函数（ResolverValue类型）
  - 参数: `event`（组件新的值）, `formModel`, `column`, `disabled`, `excontext`
  - 返回值: 无需返回
- `_d_onClear` - 点击清除按钮时触发的回调函数（ResolverValue类型）
  - 参数: `event`, `formModel`, `column`, `disabled`, `excontext`
  - 返回值: 无需返回
