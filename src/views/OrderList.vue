<template>
    <div>
        <div class="header">
            <div class="insuranceType">
                <span>车险</span>
                <span class="activeType">个险</span>
                <span>理财</span></div>
            <div class="insuranceStatus">
                <span>待支付</span>
                <span>已支付</span>
                <span>即将到期</span>
                <span>待支已失效</span>
            </div>
        </div>
        <div class="spacing"></div>
        <div class="orderWraper">
            <ul>
                <li class="orderList">
                    <div class="orderHeader">
                        <img src="https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=49366202,632101467&fm=27&gp=0.jpg" alt="">
                        <span class="insuranceTitle">保险名称保险名称保险名称保险名称保险名称</span>
                        <span class="status">核保中</span>
                    </div>
                    <div class="orderInfo">
                        <div><span class="text">被保险人:</span><span>李某某</span></div>
                        <div><span class="text">被投保人:</span><span>李某某</span></div>
                        <div><span class="text">世间:</span><span>2017-10-24 19:00</span></div>
                    </div>
                </li>
            </ul>
        </div>
    </div>
</template>
<script>
import axios from 'axios'
// import axios from '@/api/my-axios.js'
import api from '@/api/index.api'
import router from '@/router/index'
import 'swiper/dist/css/swiper.css'
import { swiper, swiperSlide } from 'vue-awesome-swiper'
export default {
    prop:{
 
    },
    components: {
      
    },
    mounted(){
        axios({
                method: 'POST',
                url: api.orderList,
                data: {
                    userId:1,
                    status: 0,
                    type: 2                }
            }).then((res) => {
                console.log("请求到的订单列表数据", res.code)
          
            }).catch(rtn => {
                console.log(rtn)
            });
   
    },
    data(){
            return{
                bannerList:[

                ],
                swiperOption: {
                    autoplay: {
                        delay: 5000,
                        disableOnInteraction: false
                    },
                    pagination: {
                        el: '.swiper-pagination',
                        clickable: true,

                    }
                }
            }
    },
      methods: {
          
  },
 
    created() {//budgetListuserId
    }
 
}
</script>
 
<style lang="less"> 
    .activeType{
           background: #FC8D00;
    }
    .header{
        box-sizing: border-box;
        height: 1.76rem;
        padding: 0.2rem 0 0.28rem 0;
        border: 1px solid red;
        .insuranceType{
            display: flex;
            width: 3.6rem;
            height: 0.64rem;
            margin:0 auto;
            font-size: 0.24rem;
            color: #fff;
            border-radius: 0.34rem;
            border: 0.01rem solid red;
            background: #E68509;
            span{
                flex: 1;
                text-align: center;
                line-height: 0.64rem;
            }
        }  
        .insuranceStatus{
            display: flex;
            height: 0.42rem;
            margin-top: 0.22rem;
            font-size: 0.28rem;
            border: 0.01rem solid red;
             span{
                flex: 1;
                text-align: center;
                line-height: 0.42rem;
                border-left: 1px solid #000;
            }
        }  
    }
    .spacing{
        height: 0.12rem;
        background: #f2f2f2
    }
    .orderWraper{
        
       .orderList{
           padding: 0 0.24rem;
           font-size: 0.28rem;
           color: #FC8D00;
            .orderHeader{
                display: flex;
                justify-content: center;
                align-items: center;
                padding: 0.16rem 0;
                border-bottom: 1px solid #000;
                img{
                    width: 1.6rem;
                    height: 0.8rem;
                }
                .insuranceTitle{
                    flex: 6;
                    box-sizing: border-box;
                    width: 2.35rem;
                    padding:0 0.15rem;
                }
                .status{
                    flex: 1.5;
                }
            }
            .orderInfo{
                box-sizing: border-box;
                height: 1.72rem;
                padding: 0.2rem 0;
                line-height: 0.32rem;   
                div{
                    padding: 0.02rem 0;
                }
            }
       }
    }
</style>
 
