<!--
 * @FilePath: /mac-ui/src/components/Login.vue
 * @Author: admin@hamm.cn
 * @Date: 2021-08-05 20:59:02
 * @LastEditTime: 2021-08-18 23:43:56
 * @LastEditors: admin@hamm.cn
 * Written by https://hamm.cn
 * @Description: 登录页面
-->

<template>
    <div class="login">
        <div class="head" :style="{backgroundImage:'url('+headImage+')'}"></div>
        <div class="message">{{haveSavedUserName?user_name:'Thinker Wing'}}</div>
        <div class="form">
            <div class="item" v-if="!haveSavedUserName" :class="isUserNameError?'error':''">
                <input class="account" placeholder="account..." type="email" v-model="user_name" />
                <!-- <i class="iconfont icon-icon_principal" @click="guest"></i> -->
            </div>
            <div class="item" :class="isUserPasswordError?'error':''">
                <input class="password" placeholder="password..." type="password" v-model="user_password"
                    :class="user_password?'password-in':''" />
                <i class="login-button iconfont icon-icon_send" :class="user_password?'click-enable':''"
                    @click="login"></i>
            </div>
        </div>
    </div>
</template>

<style scoped>
    .login {
        position: fixed;
        left: 0;
        right: 0;
        top: 0;
        bottom: 0;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        color: white;
        margin-top: -100px;
        z-index: 99999;
        backdrop-filter: blur(20px);
    }

    .head {
        background-size: 40% auto;
        background-position: center center;
        height: 150px;
        width: 150px;
        border-radius: 100%;
        box-shadow: 0px 0px 5px 5px rgba(0, 0, 0, 0.1);
        margin-top: -50px;
    }

    .message {
        margin-top: 20px;
        font-size: 20px;
        text-shadow: 0px 0px 2px 2px rgba(0, 0, 0, 0.3);
        color: #eee;
        margin-bottom: 50px;
    }

    .password {
        transition: width 0.3s;
    }

    .password-in {
        width: 155px;
    }

    .login-button {
        position: absolute;
        top: 5px;
        right: -50px;
        transition: right .3s;
    }

    .click-enable {
        right: 0;
    }

    input {
        color: white;
        outline: none;
        border: none;
        margin: 5px;
        font-size: 16px;
        background-color: rgba(255, 255, 255, 0.3);
        padding: 8px 24px;
        border-radius: 20px;
        box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.1);
        width: 100%;
    }

    .error {
        animation: loginErrorAnimation 0.2s ease 3;
    }

    ::-webkit-input-placeholder {
        color: #fff;
    }

    ::-moz-placeholder {
        color: #fff;
    }

    :-ms-input-placeholder {
        color: #fff;
    }

    .form {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .item {
        vertical-align: middle;
        position: relative;
        width: 250px;
        display: flex;
        flex-direction: row;
        justify-content: flex-start;
        align-items: center;
        overflow: hidden;
    }

    .item .iconfont {
        vertical-align: middle;
        display: inline-block;
        background-color: rgba(255, 255, 255, 0.3);
        font-size: 18px;
        border-radius: 100%;
        width: 36px;
        height: 36px;
        text-align: center;
        line-height: 36px;
        cursor: pointer;
        box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.1);
    }

    .item .iconfont:hover {
        background-color: rgba(255, 255, 255, 0.5);
    }
</style>
<script>
    export default {
        data() {
            return {
                headImage: require("@/asset/img/bg.jpg"),
                user_name: "",
                user_password: "",
                haveSavedUserName: false,
                isUserNameError: false,
                isUserPasswordError: false,
            }
        },
        created() {
            this.haveSavedUserName = false
            let user_name = localStorage.getItem("user_name") || false
            if (user_name) {
                this.user_name = user_name
                this.haveSavedUserName = true
            }
        },
        methods: {
            guest() {
                localStorage.setItem('user_name', "Guest")
                this.$emit("logined")
            },
            login() {
                if (!this.user_name) {
                    this.isUserNameError = true
                    setTimeout(() => {
                        this.isUserNameError = false
                    }, 1000)
                    return
                }
                if (!this.user_password) {
                    this.isUserPasswordError = true
                    setTimeout(() => {
                        this.isUserPasswordError = false
                    }, 1000)
                    return
                }

                this.tool.saveAccessToken("guest")
                this.$emit("logined")
                localStorage.setItem('user_name', this.user_name)
            }
        }
    }
</script>