title: Image组件
description: Image静态图片组件的用途、默认参数和可配置项说明
keywords: Image,图片组件,装饰型组件,组件配置
category: 组件菜单类
---
# Image 静态图片

## 组件用途
Image 是装饰型组件，用于在表单中展示图片。支持懒加载、预览等功能。不参与表单数据收集，仅用于展示和装饰。
- **图片展示** - 在表单中展示产品图片、头像等
- **图片预览** - 点击图片可预览大图
- **图片说明** - 配合文字说明展示图片内容

## 默认配置
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: '',
  type: 'Decorator',
  label: '新建静态图片',
  hidden: false,
  component: 'Image',
  componentProps: {
    src: '',
    fit: 'fill',
    lazy: false,
    alt: '',
    loading: 'lazy',
    hideOnClickModal: false,
    previewSrcList: [],
    zIndex: 2000,
    initialIndex: 0,
    closeOnPressEscape: true,
    previewTeleported: false,
    infinite: true,
    zoomRate: 1.2,
    minScale: 0.2,
    maxScale: 7,
    showProgress: false
  },
  componentEvent: {},
  formItemProps: {
    subLabel: ''
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
- `type` - 组件类型（固定为Decorator）
- `component` - 组件名称（固定为Image）
- `hidden` - 是否隐藏组件
- `_d_hidden` - 动态隐藏配置（ResolverValue类型）

**组件属性 (componentProps)**
- `src` - 图片地址（图片的源地址）
- `fit` - 适应方式，可选值: fill（填充）、contain（包含）、cover（覆盖）、none（无）、scale-down（缩小）
- `alt` - 替代文本（图片的替代文本）
- `lazy` - 是否启用懒加载
- `loading` - 加载方式，可选值: lazy（懒加载）、eager（立即加载）
- `previewSrcList` - 预览图片列表（开启图片预览功能，传入图片数组）
- `hideOnClickModal` - 是否可以通过点击遮罩层关闭预览
- `zIndex` - 设置图片预览的 z-index（层级）
- `initialIndex` - 初始预览图片的索引
- `closeOnPressEscape` - 是否可以通过按下 ESC 关闭预览
- `previewTeleported` - 是否将预览图片传送到 body 元素上
- `infinite` - 是否支持无限循环预览
- `zoomRate` - 图片预览的缩放比例（范围0.1-10，步长0.1）
- `minScale` - 图片预览的最小缩放比例（范围0.1-1，步长0.1）
- `maxScale` - 图片预览的最大缩放比例（范围1-20，步长0.1）
- `showProgress` - 是否显示预览进度
- `style` - 自定义样式对象

**布局属性 (layoutProps)**
- `span` - 栅格占据的列数（1-24）
- `alone` - 是否独占一行
- `colStyle` - 列自定义样式对象

**外部属性 (outsideProps)**
- `enable` - 是否启用外层包装
- `direction` - 包装方向（row、column）
- `style` - 自定义样式对象

**组件事件 (componentEvent)**
- `_d_onLoad` - 图片加载成功时触发的回调函数（ResolverValue类型）
  - 参数: `event`, `formModel`, `column`, `disabled`, `excontext`
  - 返回值: 无需返回
- `_d_onError` - 图片加载失败时触发的回调函数（ResolverValue类型）
  - 参数: `event`, `formModel`, `column`, `disabled`, `excontext`
  - 返回值: 无需返回
- `_d_onSwitch` - 切换预览图片时触发的回调函数（ResolverValue类型）
  - 参数: `event`（图片索引）, `formModel`, `column`, `disabled`, `excontext`
  - 返回值: 无需返回
- `_d_onClose` - 关闭预览时触发的回调函数（ResolverValue类型）
  - 参数: `event`, `formModel`, `column`, `disabled`, `excontext`
  - 返回值: 无需返回
- `_d_onShow` - 显示预览时触发的回调函数（ResolverValue类型）
  - 参数: `event`, `formModel`, `column`, `disabled`, `excontext`
  - 返回值: 无需返回
