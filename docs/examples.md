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
