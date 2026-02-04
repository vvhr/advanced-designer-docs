title: Table组件
description: Table表格组件的用途、默认参数和可配置项说明
keywords: Table,表格,表格组件,组件配置
category: 组件菜单类
---
# Table 可编辑表格组件

## 组件用途
Table是输入型组件，用于展示和编辑表格数据。支持行内编辑、操作列、动态添加删除行等功能，用于复杂的数据录入场景。
- **动态表格** - 需要动态添加删除行的表格数据录入
- **复杂表单** - 包含多个字段的表格形式表单
- **数据列表** - 展示和编辑列表数据

## 默认配置

```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: '',
  type: 'Inputer',
  label: '新建表格',
  hidden: false,
  value: [],
  component: 'Table',
  componentProps: {
    columns: [
      {
        key: 'name',
        field: 'name',
        label: '姓名',
        editable: true,
        editProps: {
          defaultValue: '',
          component: 'Input',
          componentProps: {
            placeholder: '请输入姓名'
          },
          formItemProps: {
            autoRules: ['isRequired']
          }
        }
      },
      {
        key: 'age',
        field: 'age',
        label: '年龄',
        editable: true,
        editProps: {
          defaultValue: 0,
          component: 'InputNumber',
          componentProps: {
            placeholder: '请输入年龄',
            min: 0,
            step: 1,
            precision: 0,
            max: 100
          },
          formItemProps: {
            autoRules: ['isRequired']
          }
        }
      },
      {
        key: 'gender',
        field: 'gender',
        label: '性别',
        editable: true,
        editProps: {
          defaultValue: '',
          component: 'Select',
          componentProps: {
            options: [
              { label: '男', value: '1' },
              { label: '女', value: '2' }
            ],
            placeholder: '请选择性别'
          },
          formItemProps: {
            autoRules: ['isRequired']
          }
        }
      },
      {
        key: 'address',
        field: 'address',
        label: '地址',
        editable: true,
        editProps: {
          defaultValue: '',
          component: 'Input',
          componentProps: {
            placeholder: '请输入地址'
          },
          formItemProps: {
            autoRules: ['isRequired']
          }
        }
      },
      {
        key: 'phone',
        field: 'phone',
        label: '电话',
        editable: true,
        editProps: {
          defaultValue: '',
          component: 'Input',
          componentProps: {
            placeholder: '请输入电话'
          },
          formItemProps: {
            autoRules: ['isRequired', 'isMobilePhone']
          }
        }
      },
      {
        key: 'action',
        label: '操作',
        type: 'action',
        editable: false,
        fixed: 'right',
        typeProps: {
          actions: [{ label: '删除', name: 'delete' }]
        }
      }
    ],
    disabled: false,
    ellipsis: false,
    align: 'left',
    headerAlign: 'left',
    rowKey: 'id',
    emptyValue: '-',
    adaptive: false,
    border: true
  },
  componentEvent: {
    _d_onAction: {
      enable: true,
      prop: 'onAction',
      value: `{{ 
        const { row, index, name } = event;
        if(name === 'delete') {
          if(formModel[column.field] !== undefined && Array.isArray(formModel[column.field])) {
            formModel[column.field].splice(index, 1);
          }
        }
        console.log('操作', row, index, name);
      }}`,
      resolver: 'COMPONENT_EVENT_FN'
    }
  },
  formItemProps: {
    noLabel: false,
    labelPosition: 'right',
    subLabel: '',
    autoRules: []
  },
  layoutProps: {
    span: 24,
    alone: true
  },
  insideProps: {},
  outsideProps: {
    enable: true,
    direction: 'column',
    style: { gap: '10px' },
    _d_prependRender: {
      enable: true,
      prop: 'prependRender',
      value: {
        type: 'el-button',
        props: { type: 'primary' },
        children: '添加',
        events: {
          click: `
            if(column.field) {
              if(!formModel[column.field] || !Array.isArray(formModel[column.field])) {
                formModel[column.field] = [];
              }
              const newRow = {};
              if(column.componentProps?.columns) {
                column.componentProps.columns.forEach(col => {
                  if(col.field && col.editable) {
                    newRow[col.field] = col.editProps?.defaultValue ?? '';
                  }
                });
              }
              formModel[column.field].push(newRow);
            }
          `
        }
      },
      resolver: 'FORM_SCHEMA_DOM_FN'
    }
  }
}
```

## 可配置属性

**基本属性**
- key: 组件唯一标识符（默认使用field值）
- field: 表单字段名，用于数据绑定（必填）
- type: 组件类型（固定为Inputer）
- component: 组件名称（固定为Table）
- hidden: 是否隐藏组件

**组件属性（componentProps）**
- value: 组件默认值（数组类型，存储表格行数据）
- columns: 列定义数组，每列包含以下属性
- key: 列的唯一标识
- field: 数据字段名
- label: 列标题
- editable: 是否可编辑
- editProps: 编辑配置
- defaultValue: 默认值
- component: 编辑组件类型
- componentProps: 编辑组件属性
- formItemProps: 编辑组件的表单项属性
- type: 列类型，如action表示操作列
- typeProps: 列类型特定属性
- fixed: 固定位置，如right表示固定在右侧
- disabled: 是否禁用整个表格
- ellipsis: 是否显示省略号
- align: 列对齐方式，可选值包括left、center、right
- headerAlign: 表头对齐方式
- rowKey: 行的唯一标识字段名
- emptyValue: 空值显示文本
- adaptive: 是否自适应
- border: 是否显示边框

**事件配置**
- _d_onAction: 操作列点击时触发（支持动态配置）
- 事件参数包含row、index、name等信息

**前置渲染配置**
- outsideProps._d_prependRender: 表格前置内容渲染
- 默认配置添加按钮，用于添加新行
- 支持动态配置，可自定义添加逻辑

**表单项属性（formItemProps）**
- noLabel: 是否不显示标签
- labelPosition: 标签位置（left、right、top）
- subLabel: 副标签文本
- autoRules: 自动校验规则数组

**布局属性（layoutProps）**
- span: 栅格占据的列数（1-24），默认24
- alone: 是否独占一行，默认true
