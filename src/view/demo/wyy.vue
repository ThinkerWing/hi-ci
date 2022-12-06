<template>
    <div class="demo">
        <div class="title">
            项目介绍：使用了vue-cli搭建项目，并且使用了fast-click，betterScroll等库完成移动端的适配和动态效果，
            项目中完成了首页、歌单详情页、搜索、播放等页面的开发，使用Vuex管理页面数据，使用vue-router 展示页面的切换。
            <br/>
        
            项目难点：使用fastclick解决移动端点击延时的缺点，并且使用betterScroll完成了歌曲播放页面中歌词滚动的效果。
            使用 vue-lazyload插件完成歌单等图片的懒加载。使用axios请求数据，且使用了async/await的语法糖来精简代码，完成复杂的请求。
            <a href="https://gitee.com/thinkerwing/travel">https://gitee.com/thinkerwing/test </a>
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