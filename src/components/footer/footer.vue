<!--脚部位置-->
<template>
    <div class="footer">
        <div class="footer-user">
            <a href="" class="btn btn-weak">登录</a>
            <span class="space-middle"></span>
            <a href="" class="btn btn-weak">注册</a>
            <div class="footer-r-city">
                城市：<span class="space-middle"></span>
                <a href="" class="btn btn-weak">广州</a>
            </div>
        </div>
        <ul class="footer-nav clearfix">
            <li class="footer-nav-li"><a href="#" class="text-blue">首页</a></li>
            <li class="footer-nav-li"><a href="" class="text-blue">我的</a></li>
            <li class="footer-nav-li"><a href="" class="text-blue">美团下载</a></li>
            <li class="footer-nav-li"><a href="" class="text-blue">电脑版</a></li>
            <li class="footer-nav-li"><a href="" class="text-blue">帮助</a></li>
        </ul>
        <div class="text-small">
            友情链接：
            <a href="#" class="text-blue">猫眼电影</a>
            <a href="#" class="text-blue footer-margin">大众点评</a>
            <a href="#" class="text-blue">大众点评下载</a>
        </div>
        <div class="footer-copyright">
            <span>@2017 小明工作室</span>
        </div>
    </div>
</template>

<script>
    
</script>

<style lang="less" rel="stylesheet/less" scope>
    .footer{
        margin-top: .3rem;
        padding: 0 .2rem .4rem;
        background-color: #f0efed;
    }
    .footer-user{
        margin-bottom: .4rem;
    }
    .footer-r-city{
        float: right;
    }
    .footer-nav{
        margin-bottom: .28rem;
    }
    .footer-nav-li{
        float: left;
        width: 20%;
        border-right: 1px solid #000;
        box-sizing: border-box;
        text-align: center;
        font-size: .24rem;
        &:last-child{
            border-right: none;
        }
    }
    .footer-margin{
        margin: 0 .5rem;
    }
    .footer-copyright{
        font-size: .22rem;
        text-align: center;
        position: relative;
        margin-top: .3rem;
        span{
            position: relative;
            padding: 0 .3rem;
            background-color: #f0efed;
            z-index: 1;
        }
        &:after{
            display: block;
            content: "";
            width: 100%;
            position: absolute;
            top: 50%;
            border-top: 1px solid #999;
        }
    }
</style>
