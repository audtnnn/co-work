<template>
    <header id="header" class="row">
        <h1>
            <router-link to="/"><img src="../../assets/image/logo_px.png" alt=""></router-link>
        </h1>
        <nav class="header__nav">
            <div class="event">
                <router-link to="/event">이벤트</router-link>
            </div>
            <div class="customer">
                <router-link to="/customer">고객센터</router-link>
            </div>
            <div class="Store_entry">
                <router-link to="/Practice">입점문의</router-link>
            </div>
            <div @click="menuOnOff" class="menu">
                <div class="bar">
                    <i class="fa-solid fa-bars"></i>
                </div>
                <div class="profile">
                    <i class="fa-solid fa-user"></i>
                </div>
                <ul v-show="menuOpen" class="menu__contents">
                    <li>
<<<<<<< HEAD
                        <a>
                            로그인/회원가입
                        </a>
=======
                        <router-link to="/practice">
                            사업제휴 / 입점문의
                        </router-link>
>>>>>>> 21aa56f56c43f1607e42fa650d915f79c0180b2f
                    </li>
                    <li>
                        <a href="#">
                            로그인 / 회원가입
                        </a>
                    </li>
                </ul>
            </div>
        </nav>
    </header>
</template>

<script>
    export default {
        name: "Header",
        data(){
            return {
                menuOpen : false
            }
        },
        methods: {
            menuOnOff(){
                this.menuOpen = !this.menuOpen;
            }
        }
    }
</script>

<style lang="scss" scoped>
    #header {
        height: 75px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        h1 {
            width: 110px;
            a {
                display: flex;
                align-items: center;
            }
        }
        .header__nav {
            width: 270px;
            height: 40px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            text-align: center;
            gap: 16px;
            .event{
                font-weight: 500;
                &:hover{
                    color: rgba(112,112,112,1)
                }
            }
            .customer{
                font-weight: 500;
                &:hover{
                    color: rgba(112,112,112,1)
                }
            }
            .Store_entry{
                font-weight: 500;
                &:hover{
                    color: rgba(112,112,112,1)
                }
            }
            .menu {
                position: relative;
                width: 76px;
                height: 40px;
                display: flex;
                align-items: center;
                gap: 6px;
                border-radius: 9999px;
                border: 1px solid rgba(235, 235, 235, 1);
                padding: 0 13px;
                cursor: pointer;
                .bar{
                    flex: 1;
                }
                .profile{
                    flex:1;
                    i { 
                        display: flex;
                        justify-content:center;
                        align-items: center;
                        color: #fff;
                        background: rgb(214,214,214);
                        width: 24px;
                        height: 24px;
                        border-radius: 50%;
                        font-size: 12px;
                    }
                }
                .menu__contents {
                    align-content: center;
                    width: 140px;
                    height: 88px;
                    display: block;
                    position: absolute;
                    top: 130%;
                    left: 0;
                    background: #fff;
                    border-radius: 8px;
                    box-shadow: 0px 2px 16px rgba(0, 0, 0, 0.08);
                    padding: 8px 0;
                    text-align: start;
                    z-index: 99999;
                    li {
                        a{
                            display: block;
                        }
                        font-size: 14px;
                        padding: 8px 16px;
                        color: #333;
                        &:hover {
                            background: rgba(235, 235, 235, 1)
                        }
                    }
            }
        }
        }
    }
</style>
