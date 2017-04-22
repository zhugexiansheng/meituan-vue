<template>
    <div class="carousel-tab" 
        @touchstart="startTouch" 
        @touchmove="startMove"
        @touchend="endTouch">
        <div :style="{width: allTabWidth, transform: tabTransForm}" class="carousel-tab-list">
            <CardList class="carousel-tab-list-item" 
            v-for="item in cardList" 
            :tab-list="item.tabList" 
            :key="item.id"/>
        </div>
        <ul class="carousel-lico">
            <li v-for="item in cardList" :class="{active: item.isActive}"></li>
        </ul>
    </div>
</template>

<script>
import CardList from './list.vue'

/**
 * 模拟数据后面考虑从后台配置获取
 */
const tabList = [{
    iconCls: 'meishi',
    link: 'http://www.baidu.com',
    color: '#fd9d21',
    text: '美食'
},{
    iconCls: 'dianying',
    link: 'http://www.baidu.com',
    color: '#ff6767',
    text: '电影'
},{
    iconCls: 'jiudian',
    link: 'http://www.baidu.com',
    color: '#8a90fa',
    text: '酒店'
},{
    iconCls: 'xiuxianyule',
    link: 'http://www.baidu.com',
    color: '#fed030',
    text: '休闲娱乐'
},{
    iconCls: 'waimai',
    link: 'http://www.baidu.com',
    color: '#fd9d21',
    text: '外卖'
},{
    iconCls: 'ktv',
    link: 'http://www.baidu.com',
    color: '#fed030',
    text: 'KTV'
},{
    iconCls: 'zhoubianyou',
    link: 'http://www.baidu.com',
    color: '#fed030',
    text: '周边游'
}];

const cardTab = [
    {
        id: 1,
        isActive: true,
        tabList: tabList
    },{
        id: 2,
        isActive: false,
        tabList: tabList
    }
];

/**
 * 拖动有关组件的全局变量
 */
const start = {
    x: 0,
    y: 0
}
const delta = {
    x: 0,
    y: 0
}
let hasJudge = false;
let canSlide = false;
let lastTramsform = 0;
const winw = window.screen.width;

export default {
    name: "Carousel",
    /**
     * 只适合设置一些初始化的数据
     */
    data () {
        return {
            cardList: cardTab,
            allTabWidth: '',
            tabTransForm: 'translateX(0)'
        }
    },
    /**
     * 数据更新在生命周期函数里面使用
     */
    created () {
        this.allTabWidth = cardTab.length * 100 + '%';
    },
    /**
     * 调用的方法
     */
    methods: {
        startTouch: function(e){
            start.x = event.touches[0].pageX;
            start.y = event.touches[0].pageY;
        },
        startMove: function(e){
            // 如果只有一屏，或者是缩放操作的话，不加处理
            if ( cardTab.length <=1 
                || event.touches.length > 1 
                || event.scale && event.scale !== 1 ) {
                return;
            }
            delta.x = event.touches[0].pageX - start.x;
            delta.y = event.touches[0].pageY - start.y;
            // 只需判断一次就好
            if ( !hasJudge && Math.abs(delta.y) < Math.abs(delta.x) ) {
                hasJudge = true;

                if ( delta.x > 0 && this.cardList[0].isActive) {
                    // 向右滑，判断是否是第一屏，如果是就不处理
                    return;
                } else if ( delta.x < 0 && this.cardList[cardTab.length-1].isActive ) {
                    // 向左滑，判断是否是最后一屏，如果是就不处理
                    return;
                }
                canSlide = true;
            }
            
            if ( canSlide ) {
                e.preventDefault();
                // 从记录位置开始移动
                this.tabTransForm = 'translateX('+(delta.x + lastTramsform)+'px)';
            }
        },
        endTouch: function(e){
            // 判断滑动了多少，决定是最后显示那个tab，并且要是滑过的话，就要回到去
            // 如果是第一屏，并且滑到第二屏的距离没有超过1/3时，回到第一屏，反之去第二屏
            // 类似从第二屏到第一屏也一样
            if ( canSlide ) {
                if ( delta.x > 0 ) {
                    // 回到第一屏
                    if ( delta.x > winw/3 ) {
                        setActionTab(true, this);
                    } else {
                        setActionTab(false, this);
                    }
                } else {
                    // 去第二屏
                    if ( Math.abs( delta.x ) > winw/3 ) {
                        setActionTab(false, this);
                    } else {
                        setActionTab(true, this);
                    }
                }
            }
            // 重置所有变量
            hasJudge = false;
            canSlide = false;

            // 设置内部变量控制下面的小圆点
            function setActionTab (isFirst, self) {
                if ( isFirst ) {
                    self.tabTransForm = 'translateX(0px)';
                    self.cardList[0].isActive = true;
                    self.cardList[cardTab.length-1].isActive = false;
                    lastTramsform = 0;
                } else {
                    self.tabTransForm = 'translateX(-'+ winw +'px)';
                    self.cardList[0].isActive = false;
                    self.cardList[cardTab.length-1].isActive = true;
                    lastTramsform = -winw;
                }
            }
        }
    },
    /**
     * 注入一些组件使用，加入依赖之后也需要注入组件才能调用
     */
    components: {
        CardList
    }
}
</script>

<style lang="less" rel="stylesheet/less">
    .carousel-tab {
        background-color: #fff;
        position: relative;
        border-bottom: 1px solid #DDD8CE;
    }
    .carousel-lico{
        text-align: center;
        li {
            display: inline-block;
            width: .16rem;
            height: .16rem;
            border-radius: 50%;
            background-color: #F0EFED;
            margin: 0 .15rem;
            &.active {
                background-color: #06c1ae;
            }
        }
    }
    .carousel-tab-list {
        display: flex;
        transition: transform .2s;
    }
    .carousel-tab-list-item {
        flex: 1;
    }
</style>
