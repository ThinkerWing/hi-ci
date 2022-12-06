<!--
 * @FilePath: /MacOS/src/view/demo/colorfull.vue
 * @Author: admin@hamm.cn
 * @Date: 2021-08-13 21:00:36
 * @LastEditTime: 2021-08-13 21:32:38
 * @LastEditors: admin@hamm.cn
 * Written by https://hamm.cn
 * @Description: 常驻Dock的App
-->

<template>
    <div class="demo">
        <div class="title">
            <!-- 我的标题栏花里胡哨
            <br>你可以通过设置 <br>titleBgColor/titleColor 来修饰我 -->
            <li>Wechat 微信的名片</li>
            <li>Gitee 双击会跳转到我的Git</li>
            <li>CSDN  双击会跳转到我的博客</li>
            <li>DEMO 示例APP | 交互功能的实现</li>
            <li>网易云、简书、Travel 是项目的介绍</li>
            <div style="text-align: center;margin-top:20px;">项目完善中···</div>



            <div style="color:red">{{app && app.data}}</div>
        </div>
    </div>
</template>

<style scoped>
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
        props: {
            app: Object
        },
        created() {
        }
    }
</script>