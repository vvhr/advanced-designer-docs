title: 文档索引大纲
description: advanced-form-designer项目所有文档的目录树和索引，便于LLM根据需求查找对应文档
keywords: 索引,目录,文档结构
category: 索引
---

## 完整文档目录

**1. 项目总览**
- `overview/project-overview.md` - 项目基本信息、技术栈、核心功能概述

**2. UI类文档 - 设计器界面结构与功能**
- 设计器基本结构
  - `ui/ui-designer-structure.md` - 设计器基本UI结构和功能按钮说明
- 顶部工具栏
  - `ui-header/ui-header-left-menu.md` - 顶部左侧菜单栏功能说明（文件、编辑、视图、运行、版本、帮助）
  - `ui-header/ui-header-right-buttons.md` - 顶部右侧按钮功能说明（AI、日志、保存、关闭）
- 左侧工具栏(8个功能面板)
  - `ui-left/ui-left-toolbar-form-props.md` - 表单设置面板
  - `ui-left/ui-left-toolbar-components.md` - 组件面板
  - `ui-left/ui-left-toolbar-outline.md` - 大纲面板
  - `ui-left/ui-left-toolbar-context.md` - 上下文面板
  - `ui-left/ui-left-toolbar-form-model.md` - 数据面板
  - `ui-left/ui-left-toolbar-form-json.md` - 代码面板
  - `ui-left/ui-left-toolbar-questions.md` - 问题检查面板
  - `ui-left/ui-left-toolbar-versions.md` - 修改记录面板
- 右侧工具栏(4个配置面板)
  - `ui-right/ui-right-toolbar-props.md` - 属性面板
  - `ui-right/ui-right-toolbar-events.md` - 事件面板
  - `ui-right/ui-right-toolbar-slots.md` - 插槽面板
  - `ui-right/ui-right-toolbar-json.md` - 代码面板
- 中间画布
  - `ui/ui-canvas.md` - 中间设计器画布功能说明

**3. 数据结构类文档 - 核心数据接口定义**
- `data-interface/data-designer-form-schema.md` - DesignerFormSchema核心数据结构说明
- `data-interface/data-designer-form-props.md` - DesignerFormProps核心数据结构说明
- `data-interface/data-resolver-value.md` - ResolverValue核心数据结构说明
- `data-interface/data-form-schema-base.md` - FormSchemaBase核心数据结构说明

**4. 组件菜单类文档 - 可用组件清单**
- 原子化组件(base) - 24个基础组件
  - `component-base/alert.md` - Alert 警告提示
  - `component-base/autocomplete.md` - Autocomplete 自动补全输入框
  - `component-base/blank.md` - Blank 空白占位
  - `component-base/cascader.md` - Cascader 级联选择器
  - `component-base/checkbox.md` - Checkbox 多选框
  - `component-base/checkbox-button.md` - CheckboxButton 多选按钮
  - `component-base/divider.md` - Divider 分割线
  - `component-base/editor.md` - Editor 富文本编辑器
  - `component-base/group.md` - Group 分组容器
  - `component-base/image.md` - Image 图片展示
  - `component-base/input.md` - Input 输入框
  - `component-base/input-number.md` - InputNumber 数字输入框
  - `component-base/input-tag.md` - InputTag 标签输入框
  - `component-base/mention.md` - Mention 提及输入
  - `component-base/radio-button.md` - RadioButton 单选按钮
  - `component-base/rate.md` - Rate 评分
  - `component-base/select.md` - Select 选择器
  - `component-base/segmented.md` - Segmented 分段控制器
  - `component-base/slider.md` - Slider 滑块
  - `component-base/table.md` - Table 表格
  - `component-base/text.md` - Text 文本展示
  - `component-base/time-picker.md` - TimePicker 时间选择器
  - `component-base/time-select.md` - TimeSelect 时间选择
  - `component-base/upload.md` - Upload 文件上传
- 快捷示例组件(demo) - 11个业务组件
  - `component-demo/name-input.md` - NameInput 姓名输入
  - `component-demo/id-card-input.md` - IdCardInput 身份证输入
  - `component-demo/phone-input.md` - PhoneInput 手机号输入
  - `component-demo/email-input.md` - EmailInput 邮箱输入
  - `component-demo/credit-code-input.md` - CreditCodeInput 统一社会信用代码输入
  - `component-demo/address-input.md` - AddressInput 地址输入
  - `component-demo/birthday-date-picker.md` - BirthdayDatePicker 生日选择器
  - `component-demo/range-date-picker.md` - RangeDatePicker 日期范围选择器
  - `component-demo/gender-radio.md` - GenderRadio 性别单选
  - `component-demo/nation-select.md` - NationSelect 民族选择
  - `component-demo/bdc-combo-input.md` - BdcComboInput 不动产组合输入
