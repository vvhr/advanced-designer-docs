title: 项目总览
description: advanced-form-designer项目的基本信息、技术栈、核心功能概述
keywords: 项目介绍,技术栈,功能概述,Vue3,表单设计器
category: 总览
---

## 项目基本信息

- **项目名称**: advanced-form-designer
- **版本**: 0.1.1
- **描述**: 基于Vue3 + Element Plus + Advanced Ele UI的低代码表单设计器

## 技术栈

- **核心框架**: Vue 3.4.0 (Composition API)
- **UI组件库**: Element Plus 2.11.7
- **高级表单组件**: advanced-ele-ui 0.2.1
- **状态管理**: Pinia 2.1.7
- **拖拽排序**: SortableJS 1.15.6
- **代码编辑器**: CodeMirror (@codemirror/*)
- **构建工具**: Vite 5.0.0
- **类型系统**: TypeScript 5.3.3
- **样式方案**: Less + UnoCSS

## 核心功能

- **可视化表单设计** - 通过拖拽方式快速构建表单，支持实时预览和编辑。设计器提供IDE风格的布局，包含顶部工具栏、左侧组件面板、中间画布、右侧属性面板
- **组件库支持** - 内置丰富的表单组件库，包括基础输入组件（Input、Select、DatePicker等）和业务场景组件（姓名输入、身份证输入、手机号输入等）
- **动态配置引擎** - 支持通过ResolverValue机制实现动态属性配置，包括表单函数、组件事件函数、立即执行函数和DOM渲染函数四种解析类型
- **数据模型管理** - 提供表单数据模型实时预览和编辑功能，支持查看表单值的实时变化
- **上下文配置** - 支持配置表单的外部上下文对象，为组件提供动态数据和方法
- **问题检查** - 自动检测表单配置中的错误和警告，帮助快速定位问题
- **版本管理** - 记录表单的修改历史，支持版本切换（功能开发中）
- **AI助手** - 集成AI智能助手，提供表单设计建议和帮助

## 项目结构

核心模块位于 `src/desginer` 目录：
- `Designer.vue` - 主容器组件
- `layout/` - 布局组件（Header、LeftPanel、RightPanel等）
- `stores/` - Pinia状态管理（designer、canvas、ui、workspace、internalLog）
- `config/` - 组件配置（base原子组件、demo示例组件）
- `types/` - TypeScript类型定义
- `hooks/` - 组合式函数（actions、sortable等）
- `components/` - 可复用组件（FnEditor、JsonEditor等）
- `utils/` - 工具函数（schema-resolver、notification等）

## 运行方式

- **开发环境**: `pnpm dev` (端口5174)
- **生产构建**: `pnpm build`
- **类型检查**: `pnpm check`

## 通信机制

设计器运行在iframe中，通过postMessage与父窗口通信：
- **父窗口 → 设计器**: `init`（初始化）、`setExcontext`（设置上下文）
- **设计器 → 父窗口**: `designer-close`（关闭）、`designer-save`（保存）
- **父窗口 → 设计器**: `designer-save-success`（保存成功）、`designer-save-failed`（保存失败）
