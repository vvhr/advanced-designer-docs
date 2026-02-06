title: DesignerFormProps数据结构
description: DesignerFormProps核心数据结构说明，定义表单设计器提供的表单设置配置结构
keywords: DesignerFormProps,表单属性,表单配置,全局配置
category: 数据结构类
---

## 概述
DesignerFormProps定义了表单设计器提供的表单全局属性配置，影响整个表单的展示和行为。这些属性会传递给AeForm组件。

- DesignerFormProps会直接传递给AeForm组件
- 某些属性的修改会影响整个表单的行为
- 建议在表单设置面板中配置，避免直接编辑JSON
- `designable`属性在设计器中自动管理，通常不需要手动设置
- 当前表单设计器不支持设置`stepValue`
- 当前表单设计器不支持设置`type='desc'`模式

## 类型定义
```typescript
interface DesignerFormProps {
  stepValue?: number | null              // 分步表单的当前激活步骤索引，默认null
  disabled?: boolean                     // 是否禁用整个表单，默认false
  type?: 'form' | 'desc'                // 表单类型，默认'form'
  size?: 'small' | 'default' | 'large'  // 表单尺寸，默认'default'
  designable?: boolean                   // 是否启用设计模式，默认true
  schemaProps?: FormSchemaProps          // 表单的SchemaProps配置
  labelWidth?: string | number           // 表单标签的宽度
  showErrorNotice?: boolean              // 是否显示错误提示，默认true
  autoInitField?: boolean                // 是否自动初始化字段默认值，默认false
}
```

## 属性详解
**stepValue** - 分步表单步骤索引
- 类型: `number | null`
- 默认值: `null`
- 用途: 当表单类型为分步表单时，设置当前激活的步骤索引
- 示例: `stepValue: 0` 表示第一步

**disabled** - 禁用整个表单
- 类型: `boolean`
- 默认值: `false`
- 用途: 禁用后所有组件不可交互
- 场景: 查看模式、审批流程中的已完成步骤

**type** - 表单类型
- 类型: `'form' | 'desc'`
- 默认值: `'form'`
- 用途:
  - `'form'` - 表单模式，用于数据录入
  - `'desc'` - 描述列表模式，用于数据展示

**size** - 表单尺寸
- 类型: `'small' | 'default' | 'large'`
- 默认值: `'default'`
- 用途: 统一控制表单组件的尺寸
- 影响: 所有输入组件、按钮等的大小

**designable** - 设计模式
- 类型: `boolean`
- 默认值: `true`
- 用途: 设计模式下显示组件边框和操作手柄
- 场景: 设计器中为`true`，运行时为`false`

**schemaProps** - 高级表单属性
- 类型: `FormSchemaProps`
- 默认值: `undefined`
- 用途: 配置表单的高级属性
- 包含: 更多Element Plus Form组件的原生属性

**labelWidth** - 标签宽度
- 类型: `string | number`
- 默认值: `undefined`
- 用途: 设置表单标签的统一宽度
- 示例: `'120px'` 或 `120`

**showErrorNotice** - 错误提示
- 类型: `boolean`
- 默认值: `true`
- 用途: 控制表单提交校验失败时是否显示错误提示信息

**autoInitField** - 自动初始化字段
- 类型: `boolean`
- 默认值: `false`
- 用途: 控制字段的自动初始化行为
- 说明: 启用后会自动将schema中的value值初始化到表单数据中
