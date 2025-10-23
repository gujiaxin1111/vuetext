<template>
<div class="shijianxiushifu">
   <h3>事件修饰符</h3>
   <a @click="click11" href="https://www.baidu.com">百度百度</a>

   <div @click="clickDiv">
    <p @click.stop="clickP">测试冒泡</p>
   </div>
</div>
</template>

<script>
export default {
    name: 'shijianxiushifu',
     data() {
         return {
            
            } 
        }, 
        methods: {
            click11(e){
                console.log('点击了解百度')
            },
            clickDiv() {
                console.log('点击了div')
            },
            clickP() {
                console.log('点击了p')
            }
        }
    }
</script>
<style scoped>
.shijianxiushifu { 
    color: yellow;
     }
</style>