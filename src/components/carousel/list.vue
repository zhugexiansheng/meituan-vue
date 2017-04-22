<template>
    <ul class="carousel-list clearfix">
        <li class="carousel-list-li" v-for="item in tabList" v-once>
            <a :href="item.link" class="carousel-list-li-a">
                <span 
                    class="iconfont" :class="item.iconCls" 
                    :style="{backgroundColor:item.color}">
                </span>
                {{item.text}}
            </a>
        </li>
    </ul>
</template>

<script>
export default {
    name: "CardList",
    props: {
        tabList: {
            type: Array,
            default: []
        }
    }
}
</script>

<style lang="less" rel="stylesheet/less">
    .carousel-list-li {
        float: left;
        width: 20%;
    }
    .carousel-list-li-a {
        display: block;
        padding: .2rem 0;
        text-align: center;
        font-size: .24rem;
        color: #666;
        .iconfont {
            display: block;
            margin: auto;
            margin-bottom: .14rem;
            width: .8rem;
            height: .8rem;
            border-radius: 10rem;
            text-align: center;
            line-height: .8rem;
            font-size: .5rem;
            color: #fff;
        }
    }
</style>
