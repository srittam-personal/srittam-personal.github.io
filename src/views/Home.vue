<template>
  <div class="pdp-container">
    <p class="back container">
        <img src="../assets/images/back-arrow.svg" alt="right arrow">
        <span class="breadcrum-menu">MEN</span>
      </p>
    <div class="pdp-content container">
      
      <div class="home-content__right">
        <ul class="product-slider" v-if="domLoaded">
          <carousel :per-page="1"  :mouse-drag="false" :navigationEnabled="true" :paginationEnabled="false" :navigateTo='navigateTo'>
            <slide v-for="product in products" :key="product.id">
              <li>
                  <img :src="product.url" alt="">
              </li>  
            </slide>          
          </carousel>
        </ul> 
        <ul class="related-prd-section">
            <li v-for="(product,index) in products" :key="product.id" @click="navigateTo =index" class="related-prd-section__img">
                <img :src="product.url" alt="" width="50">
            </li> 
        </ul>
      </div>           
      
      <div class="pdp-content__left">

        <div class="pdp__content-one"> 
          <h1 class="pdp__title">Red Canvas</h1>
          <span class="pdp__badge">OCA LOW</span>
        </div>

        <div class="pdp__content-two">
          <p class="price">$79 USD</p>
          <span class="reviews">
            <img alt="logo" src="../assets/images/reviews.svg">
            <span>154 Reviews</span>
          </span>
        </div>
        <div class="tabs">
        <ul class="pdp__content-three">
          <li class="pdp__tab" v-on:click="activetab='1'" v-bind:class="[ activetab === '1' ? 'active' : '' ]">
            <span class="tab-title" >MEN</span>
          </li>
          <li class="pdp__tab" v-on:click="activetab='2'" v-bind:class="[ activetab === '2' ? 'active' : '' ]"><span class="tab-title" >WOMEN</span></li>
        </ul>

        <div class="pdp__content-three">
            <div class="tab-content" v-if="activetab ==='1'">
              <div class="color-section">
                <span class="title">select color</span>
                <ul class="colors">
                  <li class="white"></li>
                  <li class="yellow active"></li>
                  <li class="red"></li>
                  <li class="white"></li>
                  <li class="yellow"></li>
                  <li class="red"></li>
                  <li class="white"></li>
                  <li class="yellow"></li>
                  <li class="red"></li>
                </ul>
              </div>
              <div class="size-section">
                <span class="title">select size</span>
                <a href="javascript:void(0)"  class="size-fit">Size & Fit guide</a>
                <ul class="size">
                  <li>5</li>
                  <li>6.5</li>
                  <li>7.5</li>
                  <li>5</li>
                  <li>6.5</li>
                  <li class="active">7.5</li>
                  <li class="disabled">5</li>
                  <li>6.5</li>
                  <li>7.5</li>
                  <li>5</li>
                  <li>6.5</li>
                  <li>7.5</li>
                </ul>
              </div>
            </div>
            <div class="tab-content" v-if="activetab ==='2'">
              <div class="color-section">
                <span class="title">select color</span>
                <ul class="colors">
                  <li class="yellow"></li>
                  <li class="red"></li>
                  <li class="white"></li>
                  <li class="yellow"></li>
                  <li class="white active"></li>
                  <li class="yellow"></li>
                  <li class="red"></li>
                  <li class="white"></li>                  
                  <li class="red"></li>
                </ul>
              </div>
              <div class="size-section">
                <span class="title">select size</span>
                <a href="javascript:void(0)" class="size-fit">Size & Fit guide</a>
                <ul class="size">
                  <li>7.5</li>
                  <li>5</li>
                  <li>6.5</li>
                  <li>7.5</li>
                  <li>5</li>
                  <li class="disabled">5</li>
                  <li>6.5</li>
                  <li>7.5</li>
                  <li class="active">5</li>
                  <li>6.5</li>                  
                  <li>6.5</li>
                  <li>7.5</li>
                </ul>
              </div>
            </div>
        </div>
        </div>
        <button type="submit" title="Add to bag" class="tocart" id="product-addtocart-button"><span>Add to bag</span></button>
        <p class="worldwide-shipping">Worldwide Shipping + Free Returns</p>
      </div>
      
    </div>
    <div class="pdp-related">
        <div class="related-products">        
          <div class="container">
              <h2 class="related-product__title">You'll Also Like</h2>

              <ul>
                  <carousel :per-page="4"  :mouse-drag="false" :navigationEnabled="true"
                  :per-page-custom="[[320, 2], [1024, 4]]">
                      <slide v-for="product in products" :key="product.id">
                          <li>
                              <img :src="product.url" alt="">
                              <div class="prd-details">
                                <span class="related-products__name">{{product.name}}</span>
                                <span class="related-products__price">${{product.price}}</span>
                              </div>
                          </li>  
                      </slide>          
                  </carousel>
              </ul>
          </div>
        </div>
    </div>
  </div>
</template>

<script>
//import HomeBottom from '../components/home/HomeBottom.vue';
import HomeRight from '@/components/home/HomeRight.vue';
import axios from 'axios';
import { Carousel, Slide } from 'vue-carousel';

export default {
  name: 'home',
  components: {
    //HomeBottom,    
     HomeRight,
      Carousel,
      Slide
  },

  data(){
    return{
      products : [],
      activetab: '1',
      domLoaded : false,
      navigateTo : 0
    }
  },

  async mounted(){
    try {
        const res = await axios.get('https://api.myjson.com/bins/cktyn');
        this.products = res.data;
        this.domLoaded = true;
        } catch (error) {
            console.log(error) // eslint-disable-line
        }
  }
}
</script>

<style lang="scss" scoped>
  .related-prd-section{
    text-align: center;
    height: 60px;
    overflow-y: hidden;
  }
  .related-prd-section__img{
    display: inline-block;
    padding: 3px;
    cursor: pointer;
  }
  .related-products{
    background: #f1f1f1;
    padding: 24px 0 38px 0;
    margin-bottom: 80px;
    margin-top: 35px;
    .prd-details{
      span{
        display: block;
        font-family: 'GothamHTF-Book';
        text-transform: capitalize;
        padding-top: 6px;
        padding-left: 10px;
        &.related-products__name{
          font-size: 16px;
        } 
        &.related-products__price{
          font-size: 14px;
        }
      }
    }

    &::v-deep .VueCarousel {
        .VueCarousel-navigation-button{
          font-size: 0;
          height: 38px;
          width: 20px;
          &.VueCarousel-navigation-prev{
            background: url("../assets/images/right-arrow.svg") no-repeat;
            transform: rotate(180deg) translateY(-50%) translateX(100%);
            top:35%;
            left: -10px;
          }
          &.VueCarousel-navigation-next{
            background: url("../assets/images/right-arrow.svg") no-repeat;
            right: -10px;
          }
        }
        .VueCarousel-slide {
            padding: 0 5px;
        } 
        .VueCarousel-pagination{           
            .VueCarousel-dot{
              display: none;
            }
        }     
    }
  }

  .breadcrum-menu{
    padding-left: 6px;
  }
  
  .related-product__title{
    color:#4A4A4A;
    font-family: 'Gotham-Medium';
    font-size:24px;
    font-weight: normal; 
  }
  .pdp-container{
    padding-top: 32px;
    .back{
      font-size: 10px;      
    }
  }
  .pdp-content{
    &:after{
      content: "";
      clear: both;
      display: block;
    }
  }
  .pdp__badge,.reviews {
    color: #4A4A4A;
    font-size: 12px;
    font-family: 'GothamHTF-Book';
  }
  .pdp__badge{
    display: block;
  }
  .pdp__title{
    font-family: 'Gotham-Medium';
    font-size: 24px;
    font-weight: normal;
    margin: 20px 0 6px;
  }
  .home-content__right{
    width: 66.4%;
    float: right;
    margin-top: 20px;
    &::v-deep .VueCarousel {
        .VueCarousel-navigation-button{
          font-size: 0;
          height: 38px;
          width: 20px;
          &.VueCarousel-navigation-prev{
            background: url("../assets/images/right-arrow.svg") no-repeat;
            transform: rotate(180deg) translateY(-50%) translateX(100%);
          }
          &.VueCarousel-navigation-next{
            background: url("../assets/images/right-arrow.svg") no-repeat;
          }
        }
        .VueCarousel-slide {
            padding: 0 5px;
        }      
    }
  }
  .pdp-content__left{
    width: 30%;
    float:left;
    .price{
      color: #4A4A4A;
      font-size: 16px;
      font-family: 'GothamHTF-Book';
    }
    .pdp__content-one{
        float: left;
        width: 47%;
    }
    .pdp__content-two{
        float: left;
        width: 53%;
    }
    .pdp__content-two{
      text-align:right;
      padding-top: 5px;
      .price{
        margin-bottom: 5px;
      } 
      .reviews{
        span{
          padding-left: 12px;
        }
      }
    }
    .tocart{
        background: #7DC242;
        border: 0;
        width: 100%;
        line-height: 60px;
        text-transform: uppercase;
        color: #fff;
        font-family: 'Gotham-bold';
        font-size: 15px;
        letter-spacing: 0.17em;
    }
    .worldwide-shipping{
      font-family: 'GothamHTF-Book';
      font-size: 12px;
      text-align: center;
      display: block;
      width: 100%;
      letter-spacing: 0.02em;
      margin-top: 20px;
    }
    .tabs{
      border: 1px solid #979797;
      margin-top: 30px;
      float: left;
    }
    .pdp__content-three{
      width:100%;
      .pdp__tab{
        display: inline-block;
        width: 50%;
        text-align: center;        
        line-height: 36px;
        cursor: pointer;
        &:first-child{
          border-right: 1px solid #979797;
        }
        &.active{
          background: #F1F1F1;
          border-bottom:1px solid #979797;; 
          .tab-title{
            color: #7DC242;
          }
        }
        .tab-title{
          font-size: 16px;
          font-family: 'Gotham-bold';        
        }       
      } 
       .tab-content{
         padding:25px 15px 27px 15px;
          .title{
            color: #4A4A4A;
            font-size: 10px;
            text-transform: uppercase;
            letter-spacing: 0.08em;
            display: inline-block;
          }
        }
        .size-section{
          margin-top: 20px;
          .size-fit{
            float: right;
            font-size: 13px;
            text-decoration: underline;
            margin-top: 10px;
          }
        }
        .colors{
          margin-top: 12px;
          &:after{
            clear: both;
            content: "";
            display: block;
          }
          >li{
            width: 24px;
            height: 24px;
            border-radius: 50%;
            border: 1px solid #C8C8C8;
            display: inline-block;
            margin: 0 5px;
            &:first-child{
              margin-left: 0;
            }
            &.active{
              border:2px solid #7DC242;
            }
            &.white{
              background: #F7F7F7;
            }
            &.yellow{
              background: #FFCF60;
            }
            &.red{
              background: #BB0D0F;
            }
          }
        }
        .size{
          margin-top:12px;
          >li{
            border:1px solid #979797;
            width: 34px;
            font-size: 14px;
            font-family: 'Gotham-bold';
            text-align: center;
            padding: 9px 0;
            display: inline-block;
            margin: 0 4px 7px;;
            &:first-child{
              margin-left: 0;
            }
            &.active{
              border:2px solid #7DC242;
            }
            &.disabled{
              background: #F1F1F1;
            }
          }
        }     
    }
  }

  @media only screen and (max-width: 768px) {
    .related-products{
      &::v-deep .VueCarousel {
          .VueCarousel-pagination{           
            .VueCarousel-dot{
              display: inline-block;
              background-color: #ccc !important;
              &.VueCarousel-dot--active{
                background-color: rgb(0, 0, 0) !important;
              }
            }
        }    
      }
    }
  }

  @media only screen and (max-width: 767px) {
    .home-content__right,.pdp-content__left{
      float: none;
      width: 100%;  
    }
    .pdp-container{
      padding-top:0;
      .back{
        padding: 20px;
      }
    }
    .pdp__title{
      font-size: 16px;
    }
    .pdp__badge{          
      font-size: 10px;
    }
    .pdp-content__left {
      .tocart{
        line-height: 42px;
      }
      .pdp__content-two .price{
        font-size: 14px;
        margin-bottom:0;
      }
      .tabs{
        margin-top: 17px;
      }
      .pdp__content-three .tab-content{
        padding: 11px 15px 19px 15px;
      }
    }
    .reviews{
      img{
        height: 11px;
      }
    }    
  }
</style>
