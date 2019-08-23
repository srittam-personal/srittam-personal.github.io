<template>
    <div class="header">
        <div class="header-container container">
            <a href="javascript:;" class="action nav-toggle mob-only" v-on:click='isOpen = !isOpen' ref="nav-toggle">
                <span class="push-lines">Toggle Nav</span> 
                <span class="push-lines"></span> 
                <span class="push-lines"></span>
            </a>
            <ul class="nav" v-bind:class="[ isOpen === true ? 'active' : '' ]">
                <li class="mob-only close" v-on:click='isOpen = !isOpen'>X</li>
                <router-link to="/men" v-slot="{ href, isActive }">
                    <li :class="[isActive && 'active']" class="nav__item">
                        <a :href="href" class='nav__link'>men</a>
                    </li>
                </router-link>
                <router-link to="/women" v-slot="{ href, isActive }">
                    <li :class="[isActive && 'active']" class="nav__item">
                        <a :href="href" class='nav__link'>women</a>
                    </li>
                </router-link>
                <router-link to="/about" v-slot="{ href, isActive }">
                    <li :class="[isActive && 'active']" class="nav__item about">
                        <a :href="href" class='account-cart__link'>about</a>
                    </li>
                </router-link>
            </ul>
            <div class="logo">
                <router-link to="/" class="logo__img"><img alt="logo" src="../../assets/images/logo.svg"></router-link>
            </div>
            <ul class="account-cart">
                <router-link to="/about" v-slot="{ href, isActive }">
                    <li :class="[isActive && 'active']" class="nav__item">
                        <a :href="href" class='account-cart__link'>about</a>
                    </li>
                </router-link>
                <li class="account">
                    <span class="account__icon"><img alt="logo" src="../../assets/images/account.svg"></span>
                    <div class="account__dropdown"></div>
                </li>
                <li class="cart">
                    <span class="cart__icon"><img alt="logo" src="../../assets/images/cart.svg"></span>
                    <span class="cart__count"></span>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
    export default {
        name:'header',
        data(){
            return{
                isOpen : false
            }            
        },
        methods:{
            onClose(){
                this.isOpen = false;
            }
        }
    }
</script>

<style lang="scss" >
    .header{
        border-bottom:1px solid #ccdddd; 
        padding:24px 0 16px 0;
    }
    .header-container {
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: space-between;
        .nav,.account-cart{
            height: 100%;
            align-items: center;
            display: flex;
            flex: 2;
            &__link{
                font-size: 12px;
                text-transform: uppercase;
                display: block;
                font-family: 'Gotham-bold';
                letter-spacing: 0.1em;
            }
        }
        .nav{
            .nav__item{
                margin-right: 43px;
                &.about{
                    display: none;
                }
            }
        }
        .account-cart{
            >li{
                margin-left: 21px;
                &.nav__item{
                    margin-right: 20px;
                }
            }
        }
        .account-cart{
            justify-content: flex-end;
        }
        .logo{
            flex: 1;
            text-align: center;
            &__img{
                display: inline-block;
                max-width: 75px;
            }
        }
        .nav-toggle{
            width: 25px;
            height: 35px;
            box-sizing: border-box;
            cursor: pointer;
            font-size: 0;
            z-index: 14;
            padding: 2px 0 0;
            .push-lines{
                width: 18px;
                height: 2px;
                background: #535350;
                position: relative;
                margin: 0 0 5px;
                display: block;
            }
        }
    }
    @media only screen and (max-width: 768px) {
        .header-container {
           .nav{
                display: none;
                
                &.active{
                    background-color: #3f3f41;
                    height: 100%;
                    left: 0;
                    overflow-x: hidden;
                    padding-top: 60px;
                    position: fixed;
                    top: 0;
                    transition: .5s;
                    width: 0;
                    z-index: 1000;
                    top: 0;
                    width: 300px;
                    height: 100%;
                    display: block;
                    padding: 10px;
                    .nav__link{
                        color: #fff;
                        padding: 10px 20px;     
                    }
                    .close{
                        color: #fff;
                        font-size: 16px;
                        float: right;
                        cursor: pointer;
                    }
                }
        
            } 
            .account-cart{
                .nav__item{
                     display: none;
                }
            }
            .account-cart,.logo,.nav-toggle{
                flex: 1;
            }
            
        }
    }
</style>

        