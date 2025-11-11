<template>
    <hr>
    <h3>组件自定义事件</h3>
    <zichuanfu @someEvent="getmsg"></zichuanfu>
    <p>从子组件接收到的数据：{{ message }}</p >
</template>

<script>
import zichuanfu from '../pages/zichuanfu.vue';
export default {
    name: 'zujianshijian',
    data() {
        return {
            message: ''
        }
    },

    components: {
        zichuanfu
    },
    methods: {
        getmsg(data) {
            this.message = data;
            console.log(data);
        }
    }
}
</script>

<style scoped>
    .zichuanfu {
        color: white;
    }
</style>