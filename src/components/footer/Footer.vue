<template>
    <div class="footer">
        <div class="footer__gurentee">
            <div class="container">
                <ul class="footer__gurentee-list"> 
                    <li class="footer__secure-payment desktop-only">
                        <span class="footer__gurentee-text">
                            <span class="lock-img"><img alt="lock-img" src="../../assets/images/lock.svg"></span>
                            <span class="secure-text">secure payment</span>
                        </span>
                    </li>
                    <li class="footer__express-shipping">
                        <span class="footer__gurentee-text">
                            <span class="lock-img"><img alt="logo" src="../../assets/images/lock.svg"></span>
                            <span class="secure-text">express shipping</span>
                        </span>
                    </li>
                    <li class="footer__free-returns">
                        <span class="footer__gurentee-text">
                            <span class="lock-img"><img alt="logo" src="../../assets/images/lock.svg"></span>
                            <span class="secure-text">free returns</span>
                        </span>
                    </li>
                </ul>
            </div>            
        </div>
        <div class="footer__links">
            <div class="container">
                <div class="footer__links-list">
                    <div class="footer__list first desktop-only">
                        <span class="title">men</span>
                        <ul class="links">
                            <li><a href="">OCA Low</a></li>
                            <li><a href="">OCA High</a></li>
                            <li><a href="">CATIBA Low</a></li>
                            <li><a href="">CATIBA Low</a></li>
                        </ul>
                    </div>
                    <div class="footer__list second desktop-only">
                        <span class="title">women</span>
                        <ul class="links">
                            <li><a href="">OCA Low</a></li>
                            <li><a href="">OCA High</a></li>
                            <li><a href="">CATIBA Low</a></li>
                            <li><a href="">CATIBA Low</a></li>
                        </ul>
                    </div>
                    <div class="footer__list third desktop-only">
                        <span class="title">support</span>
                        <ul class="links">
                            <li><a href="">FAQ</a></li>
                            <li><a href="">Returns</a></li>
                            <li><a href="">Live Chat</a></li>
                        </ul>
                    </div>
                    <div class="footer__list fourth desktop-only">
                        <span class="title">about</span>
                        <ul class="links">
                            <li><a href="">Mission</a></li>
                            <li><a href="">Vision</a></li>
                            <li><a href="">Future</a></li>
                        </ul>
                    </div>
                    <div class="footer__list fifth desktop-only">
                        <span class="title">pop up stores</span>
                        <ul class="links">
                            <li><a href="">Find near you</a></li>
                            <li><a href="">register</a></li>
                            <li>
                                <form class="footer__find-sneaker">
                                    <input type="text" class="textbox" name="find sneaker" placeholder="Find your sneakers here" />
                                    <button class="search"></button>
                                </form>
                            </li>
                        </ul>
                    </div>
                    <div class="footer__list six ">
                        <span class="title">newsletter</span>
                        <form class="footer__newsletter">
                            <input type="text" name="find sneaker" placeholder="Enter email" class="textbox" />
                            <button class="join-us">join us</button>
                        </form>
                        <ul class="footer__social-links">
                            <li class="insta"><a href=""></a></li>
                            <li class="fb"><a href=""></a></li>
                        </ul>
                    </div>
                    <div class="footer__mob mob-only">
                        <div class="footer__mob--left">
                            <div class="footer__list first">
                                <span class="title">shop</span>
                                <ul class="links">
                                    <li><a href="">CATIBA</a></li>
                                    <li><a href="">OCA</a></li>                                
                                </ul>
                            </div>
                            <div class="footer__list second">
                                <span class="title">support</span>
                                <ul class="links">
                                    <li><a href="">FAQ</a></li>
                                    <li><a href="">Returns</a></li>
                                    <li><a href="">Live Chat</a></li>
                                </ul>
                            </div>
                        </div>
                        <div class="footer__mob--right">
                            <div class="footer__list third">
                                <span class="title">about</span>
                            </div>
                            <div class="footer__list fourth">
                                <span class="title">blog</span>
                            </div>
                            <div class="footer__list fourth">
                                <span class="title">pop up stores</span>
                            </div>
                        </div>                                                
                    </div>
                </div>
                <div class="footer__copywrite">
                    <p class="copy">Copyright © 2019 CARIUMA. All Rights Reserved. Terms of Use | Privacy Policy</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss">
    .desktop-only{
        display: block;
    }
    .mob-only{
        display: none;
    }
    .footer{
        .textbox{
            border: 0;
            background: no-repeat;
            border-bottom: 2px solid #fff;
            line-height: 24px;
            font-size: 12px;
            color: #ffffff;
            &::-webkit-input-placeholder { 
                color:#fff;
                font-size: 12px;
            }

            &:-ms-input-placeholder { 
                color: #fff;
                font-size: 10px;
            }

            &::placeholder {
                color: #fff;
                font-size: 12px;
            }
            &:focus{
                outline: 0;
            }
        }
        .footer__gurentee{
            background: #F1F1F1;
        }
        .footer__gurentee-list{
            display: flex;
            text-align: center;
            >li{
                flex:1;
                -webkit-box-flex: 1;
                -ms-flex: 1;
                padding: 10px 0;
                .footer__gurentee-text{
                    text-transform: capitalize;
                    font-size: 13px;
                    font-family: 'Gotham-Medium';
                    color: #8c8b8b;
                    display:block;                  
                    line-height: 37px;
                }
                &.footer__express-shipping{
                    .footer__gurentee-text{
                        border-left: 1px solid;
                        border-right: 1px solid;
                    }
                }
                .lock-img{
                    width: 20px;
                    display: inline-block;
                    margin: 0 10px;
                    position: relative;
                    top: 4px;           
                }
            }
        }
        .footer__links{
            background: #000000;
            color: #D8D8D8;
            .title{
                text-transform: uppercase;
                font-family: 'Gotham-bold';
                font-size: 12px;
                    letter-spacing: 0.18em;
            }
            ul.links{
                padding-top: 8px;
                a{
                    color: #D8D8D8;
                    font-family: 'GothamHTF-Book';
                    font-size: 12px;
                    display: inline-block;
                    padding-bottom: 5px;
                }
            }
            .footer__links-list{
                border-bottom: 1px solid #979797;
                padding: 50px 0;
                &:after{
                    content: "";
                    display: block;
                    clear: both;
                }
            }
            .footer__list{
                flex: 1;
                float: left;
                width: 13.8%;
                &.six{
                    width: 22%;                    
                    margin-left: 5.6%;
                }
            }
            .copy{
                font-family: 'Gotham-Medium';
                font-size:12px;
                color: #979797;
                text-align: center; 
                padding: 22px 0;
                margin: 0;
            }
            .search{
                background: url("../../assets/images/search.svg") no-repeat;
                width: 18px;
                height: 17px;
                border: 0;
            }
            .join-us{
                font-size: 10px;
                font-family: 'Gotham-bold';
                background: transparent;
                border: 1px solid #fff;
                color: #fff;
                text-transform: uppercase;
                letter-spacing: 0.18em;
                text-align: center;
                line-height: 37px;
                max-width: 87px;
                width: 100%;
            }
            .footer__find-sneaker{
                padding-top: 18px;
                display: flex;
                .textbox{
                    width: 92%;
                    line-height: 30px;
                    &::-webkit-input-placeholder { 
                        color:#fff;
                        font-size: 10px;
                        font-style: italic;
                    }

                    &:-ms-input-placeholder { 
                        font-size: 10px;
                        font-style: italic;
                    }

                    &::placeholder {
                        font-size: 10px;
                        font-style: italic;
                    }
                }
                .search{
                    position: relative;
                    right: 20px;
                    top: 8px;
                }
            }
            .footer__newsletter{
                display: flex; 
                padding-top:8px;                
                .textbox{
                    width: 68%;
                    margin-right: 4%;
                    display: inline-block;
                }
                .join-us{
                    display: inline-block;
                    width: 28%;
                    vertical-align: bottom;
                    width: 87px;
                    flex: 0 0 87px;
                }
            }
            .footer__social-links{
                margin-top: 40px;
                li{
                    display: inline-block;
                    a{
                        display: block;
                        width: 25px;
                        height: 25px;
                    }
                    &.insta{
                        a{
                            background: url("../../assets/images/insta.svg") no-repeat;
                        }
                    }
                    &.fb{
                        margin-left: 28px;
                        a{
                            background: url("../../assets/images/fb.svg") no-repeat;
                        }
                    }
                }
            }
        }
    }
    @media only screen and (max-width: 768px) {
        .desktop-only{
            display: none;
        }
        .mob-only{
            display: block;
        }
        .footer{
            .footer__links{
                .footer__list{
                    width: 100%;
                    &.six{
                        width: 100%;
                        margin-left: 0;
                    }
                }
                .footer__newsletter{
                    padding-top: 0;                    
                }
                .container{
                    padding: 0 40px;
                }
                .footer__links-list{
                    padding: 50px 0 25px;
                    flex-wrap: wrap;
                }
                .copy{
                    line-height: 20px;
                }
                .footer__social-links{
                    margin-top: 40px;
                    margin-bottom: 47px;
                }
            } 
            .footer__mob{
                display: flex;
                width: 100%;
                .footer__mob--left,.footer__mob--right{
                    flex: 1;
                    .footer__list{
                        margin-bottom: 30px;
                    }   
                }
            }
            .footer__gurentee-list{
                li{
                    span{
                        font-size: 10px;
                    }
                    &.footer__express-shipping{
                        span.footer__gurentee-text{
                            border-left:0; 
                            line-height: 30px;
                        }
                    }
                }                
            }
        }
        .related-products .VueCarousel .VueCarousel-navigation-button{
            display: none;
        }
    }
</style>