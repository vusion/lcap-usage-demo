<template>
    <div :class="$style.root">
        <div :class="$style.head" vusion-slot-name="head">
            <div>{{defaultHeader}}</div>
            <slot name="head"></slot>
            <s-empty v-if="!$slots.head
                    && $env.VUE_APP_DESIGNER
                    && !defaultHeader
                    && !!$attrs['vusion-node-path']">
            </s-empty>
        </div>
        <div :class="$style.body">
            <template v-for="(itemVM, index) in innerDataSource">
                <div :class="$style.bodyItem"> {{ itemVM[valueField] || index + 1}} -- {{ itemVM[titleField] || 'IDE中数据未载入'}}</div>
            </template>

        </div>
        <div :class="$style.bottom" vusion-slot-name="bottom">
            <slot name="bottom"></slot>
            <s-empty v-if="!$slots.bottom
                    && $env.VUE_APP_DESIGNER
                    && !!$attrs['vusion-node-path']">
            </s-empty>
        </div>
    </div>
</template>

<script>
import supportDatasource from "@/mixins/support.datasource";
import {SEmpty} from 'cloud-ui.vusion/src/components/s-empty.vue';

export default {
    name: 'lcap-usage-demo',
    // 引入处理数据源的混入
    mixins: [supportDatasource],
    props: {
        // 请在这里定义组件的属性
        titleField: {type: String, default: 'title'},
        valueField: {type: String, default: 'value'},
        defaultHeader: {type: String, default: '默认头部'},
    },
    components: {
        SEmpty,
    },
};
</script>

<style module>
.root {
}
.root .head {
    padding: 10px;
    border-bottom: 1px solid #e8e8e8;
}
.root .body {
    padding: 10px;
    border-bottom: 1px solid #e8e8e8;
}
.root .bodyItem {
    padding: 5px 0;
    border-bottom: 1px solid #e8e8e8;
}
.root .bottom {
    padding: 10px;
    border-top: 1px solid #e8e8e8;
}
</style>
