<template>
    <div class="notice">
        <div class="mask"></div>
        <div class="noticeBox">
            <div class="title">{{$t('notice.title')}}</div>
            <div class="content">
                <div class="contentTitle">{{$t('notice.text')}}</div>
                <div class="contentText">{{$t('notice.content')}}
                </div>
            </div>
            <div class="btn">{{$t('notice.iknow')}}</div>
        </div>
    </div>
</template>

<script>
export default {

}
</script>

<style lang="less" scoped>
.notice{
    .mask{
        width: 100vw;
        height: 100vh;
        background: #000000;
        opacity: 0.5;
        position: fixed;
        left: 0;
        top: 0;
        z-index:1;

    }
     .noticeBox{
        width: 480rem;
        height: 687rem;
        position: absolute;
        left: 0;
        top: 0;
        bottom: 0;
        right: 0;
        margin: auto;
        background-image: url('../../../static/img/notice/noticeFrame.png');
        background-size: 100% 100%;
        z-index:1;
        box-sizing: border-box;
        padding-top:328rem;
        .title{
            font-size: 34rem;
            font-family: PangMenZhengDao;
            font-weight: 400;
            color: #000000;
        }
        .content{
            padding: 47rem 60rem 33rem 58rem;
            text-align: left;
            .contentTitle{
                font-size: 26rem;
                font-family: Source Han Sans CN;
                font-weight: bold;
                color: #000000;
                padding-bottom: 19rem;
            }
            .contentText{
                font-size: 22rem;
                font-family: Source Han Sans CN;
                font-weight: 400;
                color: #AFB1B3;
                line-height: 34rem;
            }
        }
        .btn{
            width: 260rem;
            height: 68rem;
            background: #082850;
            border-radius: 34rem;
            font-size: 26rem;
            font-family: Adobe Heiti Std;
            font-weight: normal;
            color: #FFFFFF;
            line-height: 68rem;
            text-align: center;
            margin: 0 auto;
        }

    }
}
</style>