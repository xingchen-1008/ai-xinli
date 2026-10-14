<template>
    <el-form>
        <template v-for="item in formItem" :key="item.prop">
            <el-form-item :label="item.label" :prop="item.prop">
                <component :is="isComp(item.comp)" :placeholder="item.placeholder"></component>
            </el-form-item>
        </template>
    </el-form>
</template>
<script setup>
const props = defineProps({
    formItem: {
        type: Array,
        default: () => []
    }
})

const isComp = (comp) => {
    return {
        input:'elInput',
        select:'elSelect'
    }[comp]
}
</script>
