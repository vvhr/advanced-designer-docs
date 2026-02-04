title: Upload组件
description: Upload文件上传器组件的用途、默认参数和可配置项说明
keywords: Upload,文件上传,输入型组件,组件配置
category: 组件菜单类
---
# Upload 文件上传器

## 组件用途
Upload 是输入型组件，用于上传文件。支持单文件和多文件上传，支持多种展示方式。
- **文件上传** - 上传单个或多个文件
- **图片上传** - 上传图片文件
- **附件上传** - 上传附件文件

## 默认配置
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: '',
  type: 'Inputer',
  label: '新建文件上传器',
  component: 'Upload',
  hidden: false,
  value: [],
  componentProps: {
    disabled: false,
    style: {},
    fileKeys: {
      name: 'fileName',
      url: 'fileUrl'
    },
    multiple: false,
    accept: '*',
    limit: null,
    sizeLimit: null,
    listType: 'picture',
    objectFit: 'fill'
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
- `component` - 组件名称（固定为Upload）
- `label` - 字段标签文本
- `_d_label` - 动态标签配置（ResolverValue类型）
- `hidden` - 是否隐藏组件
- `_d_hidden` - 动态隐藏配置（ResolverValue类型）
- `value` - 默认值（文件数组）
- `_d_value` - 动态默认值配置（ResolverValue类型）

**组件属性 (componentProps)**
- `disabled` - 是否禁用
- `_d_disabled` - 动态禁用配置（ResolverValue类型）
- `fileKeys` - 文件对象的键名映射（name: 文件名字段，url: 文件地址字段）
- `multiple` - 是否支持多选文件
- `accept` - 接受上传的文件类型
- `limit` - 最大允许上传个数
- `sizeLimit` - 文件大小限制
- `listType` - 文件列表的类型
- `objectFit` - 图片填充方式
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
- `_d_onExceed` - 文件超出个数限制时触发的回调函数（ResolverValue类型）
- `_d_onPreview` - 点击文件列表中已上传的文件时触发的回调函数（ResolverValue类型）
- `_d_onRemove` - 文件列表移除文件时触发的回调函数（ResolverValue类型）
