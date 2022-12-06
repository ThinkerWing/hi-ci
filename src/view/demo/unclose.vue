<!--
 * @FilePath: /MacOS/src/view/demo/unclose.vue
 * @Author: admin@hamm.cn
 * @Date: 2021-08-13 21:00:36
 * @LastEditTime: 2021-08-13 21:35:07
 * @LastEditors: admin@hamm.cn
 * Written by https://hamm.cn
 * @Description: 常驻Dock的App
-->

<template>
    <div class="demo">
        <!-- <div class="title">我无法被彻底关闭，只会被隐藏，<br>因为我 hideWhenClose = true , <br>你猜我适合做什么应用？</div> -->
        <img  class="img" src="../../asset/img/me.jpg" alt="">
    </div>
</template>

<style scoped>
    .img   {
        width: 80%;
        height: 80%;
        border-radius: 20px;
    }

    .demo {
        display: flex;
        height: 100%;
        width: 100%;
        color: #333;
        text-shadow: none;
        justify-content: center;
        align-items: center;
    }

    .title {
        font-size: 16px;
        text-align: left;
        margin: 10%;
    }
</style>
<script>
    export default {
        data() {
            return {
            }
        },
        created() {
        }
    }
</script>