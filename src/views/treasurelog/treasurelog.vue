<template>
    <div id="treasurelog">
        <themeStickyHeader></themeStickyHeader>
        <div class="content">
            <div class="tabbar-con">
                <div class="back" @click="topage('user')">
                    <img class="arrowimg" src="../../static/img/treasurelog/arrow-left.png" alt="">
                    재무 기록
                </div>
                <div class="tabbarlist">
                    <div :class="currentindex==index ? 'active':'tabbar-item'"
                         v-for="(item,index) in tabbarlist"
                         :key="index"
                         @click="changecurrent(index)">
                         {{item}}
                    </div>
                </div>
            </div>
            <div class="logcon">
                <div class="inlog" v-if="currentindex==0">
                    <div class="head">
                        <span class="head-text">동전 충전 기록</span>
                    </div>
                    <div class="table-head">
                        <div class="item1">시간</div>
                        <div class="item2">화폐종류</div>
                        <div class="item3">유형</div>
                        <div class="item4">수량</div>
                        <div class="item5">조작하다</div>
                    </div>
                    <div v-for="item in inloglist"
                         :key="item.index">
                         <coinlog :itemlog="item"></coinlog>
                    </div>

                </div>
                <div class="outlog" v-if="currentindex==1">
                    <div class="head">
                        <span class="head-text">동전 인출 기록</span>
                    </div>
                    <div class="table-head">
                        <div class="item1">시간</div>
                        <div class="item2">화폐종류</div>
                        <div class="item3">유형</div>
                        <div class="item4">수량</div>
                        <div class="item5">조작하다</div>
                    </div>
                    <div v-for="item in inloglist"
                         :key="item.index">
                        <coinlog :itemlog="item"></coinlog>
                    </div>
                </div>
                <div class="otclog" v-if="currentindex==2">
                    <div class="head">
                        <span class="head-text">OTC 거래 기록</span>
                    </div>
                    <div class="table-head">
                        <div class="item1">시간</div>
                        <div class="item2">화폐종류</div>
                        <div class="item3">유형</div>
                        <div class="item4">수량</div>
                        <div class="item5">조작하다</div>
                    </div>
                    <div v-for="item in inloglist"
                         :key="item.index">
                        <coinlog :itemlog="item"></coinlog>
                    </div>
                </div>
                <div class="locallog" v-if="currentindex==3">
                    <div class="head">
                        <span class="head-text">위치 구 매 기록</span>
                    </div>
                    <div class="table-head">
                        <div class="item1">시간</div>
                        <div class="item2">위치</div>
                        <div class="item3">유형</div>
                        <div class="item4">수량</div>
                        <div class="item5">단가</div>
                        <div class="item6">조작 하 다</div>
                    </div>
                    <gllog></gllog>
                </div>
                <div class="goodslog" v-if="currentindex==4">
                    <div class="head">
                        <span class="head-text">상점 구 매 기록</span>
                    </div>
                    <div class="table-head">
                        <div class="item1">시간</div>
                        <div class="item2">위치</div>
                        <div class="item3">유형</div>
                        <div class="item4">수량</div>
                        <div class="item5">단가</div>
                        <div class="item6">조작 하 다</div>
                    </div>
                    <gllog></gllog>
                </div>
            </div>
        </div>
        <bottom></bottom>
    </div>
</template>

<script>
    import gllog from "../../components/gllog";
    import coinlog from "../../components/coinlog/coinlog";
    import themeStickyHeader from "../../components/header/themeStickyHeader";
    import bottom from "../../components/bottom/bottom";
    export default {
        name: "treasurelog",
        components:{themeStickyHeader,bottom,coinlog,gllog},
        data(){
            return{
                tabbarlist:['동전 충전 기록','동전 인출 기록','OTC 거래 기록','위치 구 매 기록','상점 구 매 기록'],
                currentindex:0,
                inloglist:[
                    {
                        time:'2021-02-25',
                        cointype:'SLT',
                        type:'유형',
                        num:'1000000'
                    },
                    {
                        time:'2021-03-25',
                        cointype:'SLT',
                        type:'유형',
                        num:'1000000'
                    },
                    {
                        time:'2021-04-25',
                        cointype:'SLT',
                        type:'유형',
                        num:'1000000'
                    }
                ]
            }
        },
        methods:{
            changecurrent(index){
                this.currentindex = index
            },
            topage(name){
                this.$router.push({
                    name: name
                })
            }
        }
    }
</script>

<style scoped lang="less">
    #treasurelog{
        width: 1920rem;
        height: auto;
        .content{
            margin-top: 75rem;
            height: calc(100vh - 75rem - 200rem);
            .tabbar-con{
                width: 100%;
                height: 90rem;
                background-color: #041037;
                margin-bottom: 20rem;
                .back{
                    font-size: 14rem;
                    font-family: Source Han Sans CN;
                    font-weight: 400;
                    color: #FFFFFF;
                    margin-top: 60rem;
                    float: left;
                    margin-left: 360rem;
                    margin-right: 119rem;
                    .arrowimg{
                        width: 9rem;
                        height: 14rem;
                        /*float: left;*/
                        margin-right: 9rem;
                        margin-top: 2rem;
                    }
                }
                .tabbarlist{
                    width: 586rem;
                    display: flex;
                    justify-content: space-between;
                    /*margin-left: 360rem;*/
                    .tabbar-item{
                        font-size: 14rem;
                        font-family: Source Han Sans CN;
                        font-weight: 400;
                        color: #77AFE7;
                        margin-top: 60rem;
                    }
                    .active{
                        font-size: 14rem;
                        font-family: Source Han Sans CN;
                        font-weight: 400;
                        color: #FFFFFF;
                        margin-top: 60rem;
                        position: relative;
                    }
                    .active::after{
                        content:"";
                        display: inline-block;
                        position: absolute;
                        top: 20rem;
                        left: 43%;
                        width: 12rem;
                        height: 4rem;
                        background-color: #00B9FE;
                        border-radius: 4rem;
                    }
                }
            }
            .logcon{
                width: 1200rem;
                height: auto;
                margin: 0 auto;
                border: 1rem solid #E4E7ED;
                .inlog{
                    width: 1200rem;
                    height: 500rem;
                    .head{
                        width: 100%;
                        height: 50rem;
                        background: #F8FAFC;
                        border-bottom: 1rem solid #E4E7ED;
                        line-height: 50rem;
                        .head-text{
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            margin-left: 26rem;
                            float: left;
                        }
                    }
                    .table-head{
                        width: 100%;
                        height: 50rem;
                        border-bottom: 1rem solid #E4E7ED;
                        display: flex;
                        .item1{
                            line-height: 50rem;
                            margin-left: 26rem;
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            /*margin-right: 181rem;*/
                            width: 288rem;
                            text-align: left;
                        }
                        .item2{
                            line-height: 50rem;
                            /*margin-right: 172rem;*/
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            width: 219rem;
                            text-align: left;
                        }
                        .item3{
                            line-height: 50rem;
                            /*margin-right: 210rem;*/
                            width: 263rem;
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            text-align: left;
                        }
                        .item4{
                            line-height: 50rem;
                            /*margin-right: 262rem;*/
                            width: 400rem;
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            text-align: left;
                        }
                        .item5{
                            line-height: 50rem;
                            font-size: 14rem;
                            width: 104rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            text-align: left;
                        }
                    }
                }
                .outlog{
                    width: 1200rem;
                    height: 500rem;
                    margin: 0 auto;
                    .head{
                        width: 100%;
                        height: 50rem;
                        background: #F8FAFC;
                        border: 1rem solid #E4E7ED;
                        line-height: 50rem;
                        .head-text{
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            margin-left: 26rem;
                            float: left;
                        }
                    }
                    .table-head{
                        width: 100%;
                        height: 50rem;
                        border-bottom: 1rem solid #E4E7ED;
                        display: flex;
                        .item1{
                            line-height: 50rem;
                            margin-left: 26rem;
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            /*margin-right: 181rem;*/
                            width: 288rem;
                            text-align: left;
                        }
                        .item2{
                            line-height: 50rem;
                            /*margin-right: 172rem;*/
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            width: 219rem;
                            text-align: left;
                        }
                        .item3{
                            line-height: 50rem;
                            /*margin-right: 210rem;*/
                            width: 263rem;
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            text-align: left;
                        }
                        .item4{
                            line-height: 50rem;
                            /*margin-right: 262rem;*/
                            width: 400rem;
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            text-align: left;
                        }
                        .item5{
                            line-height: 50rem;
                            font-size: 14rem;
                            width: 104rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            text-align: left;
                        }
                    }
                }
                .otclog{
                    width: 1200rem;
                    height: 500rem;
                    margin: 0 auto;
                    .head{
                        width: 100%;
                        height: 50rem;
                        background: #F8FAFC;
                        border: 1rem solid #E4E7ED;
                        line-height: 50rem;
                        .head-text{
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            margin-left: 26rem;
                            float: left;
                        }
                    }
                    .table-head{
                        width: 100%;
                        height: 50rem;
                        border-bottom: 1rem solid #E4E7ED;
                        display: flex;
                        .item1{
                            line-height: 50rem;
                            margin-left: 26rem;
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            /*margin-right: 181rem;*/
                            width: 288rem;
                            text-align: left;
                        }
                        .item2{
                            line-height: 50rem;
                            /*margin-right: 172rem;*/
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            width: 219rem;
                            text-align: left;
                        }
                        .item3{
                            line-height: 50rem;
                            /*margin-right: 210rem;*/
                            width: 263rem;
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            text-align: left;
                        }
                        .item4{
                            line-height: 50rem;
                            /*margin-right: 262rem;*/
                            width: 400rem;
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            text-align: left;
                        }
                        .item5{
                            line-height: 50rem;
                            font-size: 14rem;
                            width: 104rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            text-align: left;
                        }
                    }
                }
                .locallog{
                    width: 1200rem;
                    height: 500rem;
                    margin: 0 auto;
                    .head{
                        width: 100%;
                        height: 50rem;
                        background: #F8FAFC;
                        border: 1rem solid #E4E7ED;
                        line-height: 50rem;
                        .head-text{
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            margin-left: 26rem;
                            float: left;
                        }
                    }
                    .table-head{
                        width: 100%;
                        height: 50rem;
                        border-bottom: 1rem solid #E4E7ED;
                        display: flex;
                        .item1{
                            line-height: 50rem;
                            margin-left: 26rem;
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            /*margin-right: 230rem;*/
                            width: 308rem;
                            text-align: left;
                        }
                        .item2{
                            line-height: 50rem;
                            /*margin-right: 170rem;*/
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            width: 235rem;
                            text-align: left;
                        }
                        .item3{
                            line-height: 50rem;
                            /*margin-right: 161rem;*/
                            width: 229rem;
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            text-align: left;
                        }
                        .item4{
                            line-height: 50rem;
                            /*margin-right: 170rem;*/
                            width: 228rem;
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            text-align: left;
                        }
                        .item5{
                            line-height: 50rem;
                            /*margin-right: 215rem;*/
                            width: 262rem;
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            text-align: left;
                        }
                        .item6{
                            line-height: 50rem;
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            width: 100rem;
                        }
                    }
                }
                .goodslog{
                    width: 1200rem;
                    height: 500rem;
                    margin: 0 auto;
                    .head{
                        width: 100%;
                        height: 50rem;
                        background: #F8FAFC;
                        border: 1rem solid #E4E7ED;
                        line-height: 50rem;
                        .head-text{
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            margin-left: 26rem;
                            float: left;
                        }
                    }
                    .table-head{
                        width: 100%;
                        height: 50rem;
                        border-bottom: 1rem solid #E4E7ED;
                        display: flex;
                        .item1{
                            line-height: 50rem;
                            margin-left: 26rem;
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            /*margin-right: 230rem;*/
                            width: 308rem;
                            text-align: left;
                        }
                        .item2{
                            line-height: 50rem;
                            /*margin-right: 170rem;*/
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            width: 235rem;
                            text-align: left;
                        }
                        .item3{
                            line-height: 50rem;
                            /*margin-right: 161rem;*/
                            width: 229rem;
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            text-align: left;
                        }
                        .item4{
                            line-height: 50rem;
                            /*margin-right: 170rem;*/
                            width: 228rem;
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            text-align: left;
                        }
                        .item5{
                            line-height: 50rem;
                            /*margin-right: 215rem;*/
                            width: 262rem;
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            text-align: left;
                        }
                        .item6{
                            line-height: 50rem;
                            font-size: 14rem;
                            font-family: Source Han Sans CN;
                            font-weight: 400;
                            color: #444444;
                            width: 100rem;
                        }
                    }
                }
            }
        }
    }
</style>