<template>
    <h3>插槽3再续</h3>
    <slot name="headerer" :msg="childMsg"></slot>
    <slot name="mainin" :job="jobMsg"></slot>
</template>
<script>
export default {
    name: 'slotszaixu',
    data() {
        return {
            childMsg: '这小子新泽西',
            jobMsg: '反对反对反对'
        }
    }
}
</script>
