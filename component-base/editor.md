title: Editor组件
description: Editor富文本编辑器组件的用途、默认参数和可配置项说明
keywords: Editor,富文本编辑器,输入型组件,组件配置
category: 组件菜单类
---
# Editor 富文本编辑器

## 组件用途
Editor 是输入型组件，提供富文本编辑功能。支持格式化文本、插入图片、表格等功能，用于输入富文本内容。
- **富文本编辑** - 编辑带格式的文本内容
- **内容发布** - 发布文章、公告等富文本内容
- **文档编辑** - 编辑文档、说明等

## 默认配置
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: '',
  type: 'Inputer',
  label: '新建富文本框',
  hidden: false,
  value: null,
  component: 'Editor',
  componentProps: {
    disabled: false,
    placeholder: null,
    editorHeight: 200,
    viewHeight: 200,
    mode: 'simple',
    toolbarKeys: [],
    toolbarExcludeKeys: [],
    addToolbarKeys: [],
    theme: 'light',
    contentIsMarkdown: false,
    contentRetention: false,
    contentRetentionKey: '',
    resizable: false,
    toolbarTipEnable: false,
    lang: 'zh-CN',
    editorOptions: {},
    style: {},
    freshKey: 0
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
  outsideProps: {}
}
```

## 可配置属性

**基本属性**
- `key` - 组件唯一标识符
- `field` - 字段名称，用于表单数据绑定
- `type` - 组件类型（固定为Inputer）
- `component` - 组件名称（固定为Editor）
- `label` - 字段标签文本
- `_d_label` - 动态标签配置（ResolverValue类型）
- `hidden` - 是否隐藏组件
- `_d_hidden` - 动态隐藏配置（ResolverValue类型）
- `value` - 默认值（字符串类型，HTML或Markdown格式）
- `_d_value` - 动态默认值配置（ResolverValue类型）

**组件属性 (componentProps)**
- `disabled` - 是否禁用
- `_d_disabled` - 动态禁用配置（ResolverValue类型）
- `placeholder` - 占位文本
- `editorHeight` - 编辑器高度（像素，范围0-1000）
- `viewHeight` - 预览高度（像素，范围0-1000）
- `mode` - 工具栏模式，可选值: simple（默认）、full（全功能）
- `toolbarExcludeKeys` - 工具栏排除的按钮数组，可选值包括:
  - `undo`（撤销）、`redo`（重做）、`brush`（格式刷）、`eraser`（清除格式）
  - `heading`（正文/标题）、`font-family`（字体）、`font-size`（字号）
  - `bold`（加粗）、`italic`（斜体）、`underline`（下划线）、`strike`（删除线）
  - `link`（链接）、`code`（行内代码）、`subscript`（下标）、`superscript`（上标）
  - `hr`（分割线）、`todo`（任务列表）、`emoji`（表情）、`highlight`（高亮）
  - `font-color`（字体颜色）、`align`（对齐）、`line-height`（行高）
  - `bullet-list`（无序列表）、`ordered-list`（有序列表）
  - `indent-decrease`（减少缩进）、`indent-increase`（增加缩进）
  - `break`（强制换行）、`image`（图片）、`video`（视频）、`attachment`（附件）
  - `quote`（引用）、`container`（高亮块）、`code-block`（代码块）
  - `table`（表格）、`source-code`（源代码）、`printer`（打印）
  - `fullscreen`（全屏）、`ai`（AI助手）
- `theme` - 主题，可选值: light（亮色）、dark（暗色）
- `contentIsMarkdown` - 内容是否为Markdown格式（控制输入和输出为markdown格式）
- `contentRetention` - 是否启用自动保存
- `contentRetentionKey` - 自动保存的键名
- `resizable` - 是否可调整大小
- `toolbarTipEnable` - 是否启用工具栏提示
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
