<!--导购tab-->
<template>
    <div class="shopGuide clearfix">
        <a href="#" class="shopGuide-left">
            <h1 class="shopGuild-big shopGuide-left-h1">我们约吧</h1>
            <small>恋人家人好朋友</small>
            <div class="shopGuide-left-img">
                <img src="//p0.meituan.net/mmc/fe4d2e89827aa829e12e2557ded363a112289.png" alt="">
            </div>
        </a>
        <div class="shopGuide-right">
            <a  href="#" class="shopGuide-right-top">
                <div class="shopGuide-right-top-left">
                    <h1 class="shopGuild-big text-red">低价超值</h1>
                    <small>十元惠生活</small>
                </div>
                <div class="shopGuide-right-top-right">
                    <img src="//p0.meituan.net/mmc/a06d0c5c0a972e784345b2d648b034ec9710.jpg" alt="">
                </div>
            </a>
            <div class="shopGuide-right-bottom">
                <a href="#" class="meituan-border-right">
                    <h1 class="shopGuild-small text-purple">聚餐宴请</h1>
                    <small>朋友家人常聚聚</small>
                </a>
                <a href="#">
                    <h1 class="shopGuild-small text-oringin">名店抢购</h1>
                    <small class="shopGuild-desc">距离结束</small>
                    <TimeCount end-time="2017-04-23 20:00"/>
                </a>
            </div>
        </div>
    </div>
</template>

<script>
import TimeCount from './timeCount.vue'

export default {
    name: 'shopGuide',
    components: {
        TimeCount
    }
}
</script>

<style lang="less" rel="stylesheet/less">
    .shopGuide {
        background-color: #fff;
        border-top: 1px solid #DDD8CE;
        border-bottom: 1px solid #DDD8CE;
        padding: .12rem;
        display: flex;
        overflow: hidden;
        text-align: center;
    }
    .shopGuide-left{
        flex: 1;
        border-right: 1px solid #DDD8CE;
    }
    .shopGuide-right{
        flex: 2;
    }
    .shopGuild-big{
        margin-top: .3rem;
        margin-bottom: .25rem;
        font-size: .3rem;
    }
    .shopGuild-small{
        margin-bottom: .14rem;
        margin-top: .12rem;
        font-size: .3rem;
    }
    .shopGuide-left-h1{
        color: #55a40f;
    }
    .shopGuide-left-img{
        width: 1.76rem;
        height: 1.76rem;
        margin: auto;
        display: block;
        img {
            height: 100%;
        }
    }
    .shopGuide-right-top{
        border-bottom: 1px solid #ddd8ce;
        height: 1.46rem;
        display: block;
    }
    .shopGuide-right-top-left{
        vertical-align: top;
        width: 1.7rem;
        text-align: left;
        display: inline-block;
    }
    .shopGuide-right-top-right{
        width: 1.3rem;
        height: 1.3rem;
        display: inline-block;
        margin: auto;
        img{
            height: 100%;
        }
    }
    .shopGuide-right-bottom{
        display: flex;
        text-align:left;
        a{
            flex: 1;
            height: 1.48rem;
            padding: 0 .12rem;
        }
    }
    .shopGuild-desc{
        margin-bottom: .2rem;
        display:block;
    }
</style>
