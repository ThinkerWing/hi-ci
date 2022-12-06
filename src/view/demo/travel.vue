<template>
    <div class="demo">
        <div class="title">
            项目介绍：使用vue-cli搭建项目，使用Better-scroll实现字母表布局和下拉效果，
            Vuex实现数据共享，使用LocalStorage实现页面数据持久存储，使用keep-alive优化路由页面性能，
            开发过程中使用git进⾏版本控制。 
            <br/>
        
            项目难点：通过降级解决webpack和css-loader版本不兼容，
            使用overflow:hidden解决3G⽹络测试下的外边距塌陷，在 Vue.$nextTick()钩⼦里去初始化better-scroll，
            确保DOM已经渲染，解决不能下拉的问题。 
            <a href="https://gitee.com/thinkerwing/travel">https://gitee.com/thinkerwing/travel </a>
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
        text-align: justify;
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