title: NationSelect 组件示例模板
description: NationSelect民族选择快捷示例组件的用途和默认参数说明
keywords: NationSelect,民族选择,快捷组件,示例组件
category: 示例模板类
---
# NationSelect 民族选择器示例模板

## 模板用途
NationSelect 并不是一个组件，而是针对民族选择场景的快捷示例，专门用于民族选择场景。
NationSelect 由 Select 组件实现，支持 Select 组件的所有属性和配置能力。
已预配置56个民族选项和必填校验规则。
- **用户注册** - 在用户注册表单中快速添加民族选择
- **个人信息** - 在个人信息编辑表单中使用
- **人口统计** - 在人口统计表单中使用

## 模板内容
```typescript
const defaultSchema: DesignerFormSchema = {
  key: '',
  field: 'nation',
  type: 'Inputer',
  label: '民族',
  hidden: false,
  value: '',
  component: 'Select',
  componentProps: {
    disabled: false,
    clearable: false,
    placeholder: null,
    multiple: false,
    collapseTags: false,
    collapseTagsTooltip: false,
    multipleLimit: 0,
    autocomplete: 'off',
    filterable: false,
    allowCreate: false,
    noMatchText: '无匹配数据',
    noDataText: '无数据',
    reserveKeyword: true,
    defaultFirstOption: false,
    popperAppendToBody: true,
    automaticDropdown: false,
    options: [
      { value: '01', label: '汉族' },
      { value: '02', label: '蒙古族' },
      { value: '03', label: '回族' },
      { value: '04', label: '藏族' },
      { value: '05', label: '维吾尔族' },
      { value: '06', label: '苗族' },
      { value: '07', label: '彝族' },
      { value: '08', label: '壮族' },
      { value: '09', label: '布依族' },
      { value: '10', label: '朝鲜族' },
      { value: '11', label: '满族' },
      { value: '12', label: '侗族' },
      { value: '13', label: '瑶族' },
      { value: '14', label: '白族' },
      { value: '15', label: '土家族' },
      { value: '16', label: '哈尼族' },
      { value: '17', label: '哈萨克族' },
      { value: '18', label: '傣族' },
      { value: '19', label: '黎族' },
      { value: '20', label: '僳僳族' },
      { value: '21', label: '佤族' },
      { value: '22', label: '畲族' },
      { value: '23', label: '高山族' },
      { value: '24', label: '拉祜族' },
      { value: '25', label: '水族' },
      { value: '26', label: '东乡族' },
      { value: '27', label: '纳西族' },
      { value: '28', label: '景颇族' },
      { value: '29', label: '柯尔克孜族' },
      { value: '30', label: '土族' },
      { value: '31', label: '达翰尔族' },
      { value: '32', label: '仫佬族' },
      { value: '33', label: '羌族' },
      { value: '34', label: '布朗族' },
      { value: '35', label: '撒拉族' },
      { value: '36', label: '毛南族' },
      { value: '37', label: '仡佬族' },
      { value: '38', label: '锡伯族' },
      { value: '39', label: '阿昌族' },
      { value: '40', label: '普米族' },
      { value: '41', label: '塔吉克族' },
      { value: '42', label: '怒族' },
      { value: '43', label: '乌孜别克族' },
      { value: '44', label: '俄罗斯族' },
      { value: '45', label: '鄂温克族' },
      { value: '46', label: '德昂族' },
      { value: '47', label: '保安族' },
      { value: '48', label: '裕固族' },
      { value: '49', label: '京族' },
      { value: '50', label: '塔塔尔族' },
      { value: '51', label: '独龙族' },
      { value: '52', label: '鄂伦春族' },
      { value: '53', label: '郝哲族' },
      { value: '54', label: '门巴族' },
      { value: '55', label: '珞巴族' },
      { value: '56', label: '基诺族' },
      { value: '97', label: '其他' },
      { value: '98', label: '外国血统中国籍人士' }
    ]
  },
  componentEvent: {},
  formItemProps: {
    noLabel: false,
    labelPosition: 'right',
    subLabel: '',
    autoRules: ['isRequired']
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
