<!-- 该 README.md 根据 api.yaml 和 docs/*.md 自动生成，为了方便在 GitHub 和 NPM 上查阅。如需修改，请查看源文件 -->

# LcapUsageDemo 扩展组件搭建示例

- [示例](#示例)
    - [动态数据渲染](#动态数据渲染)
- [API]()
    - [Props/Attrs](#propsattrs)
    - [Slots](#slots)

**Other**

请在这里添加描述

## 示例
### 动态数据渲染

```vue

<template>
    <div>
        <lcap-usage-demo
            :value.sync="value"
            :dataSource="dataSource"
            titleField="title"
            valueField="value"
        >
        </lcap-usage-demo>
    </div>
</template>
<script>
export default {
    data() {
        return {
            value: 1,
            dataSource: [{
                title: '数据 1',
                value: '1',
            }, {
                title: '数据 2',
                value: '2',
            }, {
                title: '数据 3',
                value: '3',
            }]
        };
    },
    methods: {
        
    },
};
</script>
```

## API
### Props/Attrs

| Prop/Attr | Type | Options | Default | Description |
| --------- | ---- | ------- | ------- | ----------- |
| data-source | Array\<Item\> \| Function \| Object |  |  | 集合类型变量或者输出参数为集合类型的逻辑 |
| data-schema | schema |  |  | 集合类型每一元素的数据类型 |
| title-field | string |  | `'title'` | 数据源集合的元素，用于显示标签标题的属性 |
| value-field | string |  | `'value'` | 数据源集合的元素，用于标识标签值的属性 |
| default-header | string |  | `'默认头部'` | 默认头部 |
| attr-A | boolean |  | `true` | 属性A控制下方属性B和属性C的显示 |
| attr-B | string |  | `''` | 属性A为true时，属性B显示 |
| attr-C | string |  | `''` | 属性A为false时，或属性B为空，属性C显示 |
| attr-D | boolean |  | `false` | 属性D |

### Slots

#### bottom

插入文本。

