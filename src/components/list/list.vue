<!--list组件-->
<template>
    <div class="guess-like">
        <div class="guess-like-list">
            <div class="guess-like-list-title">猜你喜欢</div>
            <ul class="list">
                <li v-for="good in listData" class="list-li">
                    <a :href="good.goodsHref">
                        <div class="list-li-left">
                            <img :src="good.imgSrc" alt="">
                        </div>
                        <div class="list-li-right">
                            <div class="list-li-right-h1 sigle-line">
                            {{good.title}}
                            </div>
                            <div class="list-li-right-dtl">
                            {{good.dtl}}
                            </div>
                            <div class="list-li-right-price">
                                <span class="strong">{{good.price}}</span>
                                <span class="strong-color">元</span>
                                <dl>{{good.oriPrice}}</dl>
                                <div class="line-right">已售:{{good.hasSell}}</div>
                            </div>
                        </div>
                    </a>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: 'list',
    props: {
        listData: {
            type: Array,
            default: function() {
                return [{
                    imgSrc: '//p0.meituan.net/200.0/deal/e5d21470df5ef34f92b77d83dd16c771153749.jpg@0_7_368_368a%7C267h_267w_2e_90Q',
                    title: '正新鸡排',
                    dtl: '[全国]【官方】正新鸡排尊享版单人餐',
                    price: 100,
                    oriPrice: 1000,
                    hasSell: 10000
                }]
            }
        }
    }
}
</script>

<style lang="less" rel="stylesheet/less">
    .guess-like {
        border-top: 1px solid #DDD8CE;
        border-bottom: 1px solid #DDD8CE;
        background-color: #fff;
    }
    .guess-like-list{
        padding-left: .2rem;
    }
    .guess-like-list-title{
        font-size: .34rem;
        padding: .28rem .2rem;
        color: #333;
    }
    .list-li {
        border-top: 1px solid #DDD8CE;
        padding: .28rem .2rem .28rem 0;
    }
    .list-li-left{
        width: 1.8rem;
        height: 1.64rem;
        text-align: center;
        overflow: hidden;
        float: left;
        img{
            width: 100%;
            background-size: 100%;
            background-color: #f0efed;
            border: 0;
        }
    }
    .list-li-right{
        margin-left: 2rem;
        position: relative;
        height: 1.64rem;
    }
    .list-li-right-h1{
        padding-top: .1rem;
        margin-bottom: .12rem;
        font-size: .3rem;
        font-weight: 400;
        color: #333;
    }
    .list-li-right-dtl{
        font-size: .24rem;
        height: .68rem;
        margin-bottom: .16rem;
        color: #666;
        text-overflow: ellipsis;
        display: -webkit-box;
        -webkit-line-clamp: 2;
        -webkit-box-orient: vertical;
        overflow: hidden;
    }
    .list-li-right-price{
        position: absolute;
        bottom: 0;
        width: 100%;
        dl {
            font-size: .24rem;
            margin: 0;
            padding: 0;
            display: inline-block;
            &:before{
                content: '门市价:'
            }
        }
        .line-right{
            position: absolute;
            top: .04rem;
            right: 0;
            font-size: .24rem;
        }
    }
    .strong{
        font-size: .38rem;
        color: #06c1ae;
    }
    .strong-color{
        font-size: .26rem;
        color: #06c1ae;
    }
</style>
