<template>
    <header class="navbar">
        <div class="nav-wrap-left">
            <a href="#" class="react">
                <span class="city">广州<i class="text-icon icon-downarrow"></i></span>
            </a>
        </div>
        <div class="box-search">
            <a href="#" class="search-zone">
                <i class="text-icon icon-search">⌕</i>
                <span class="single-line">输入商家/品类/商圈</span>
            </a>
        </div>
        <div class="nav-wrap-right">
            <a href="#" class="react">
                <i class="text-icon">⍥</i>我的
            </a>
        </div>
    </header>
</template>

<script>
    
</script>

<style lang="less" rel="stylesheet/less">
    @height: 1.01rem;
    @fontColor: #fff;
    .navbar{
        background-color: #06c1ae;
        border-bottom: 1px solid #21897d;
        display: flex;
        height: @height;
        .react {
            color: @fontColor;
            display: inline-block;
        }
        .nav-wrap-left {
            line-height: @height;
            text-align: center;
            .city {
                line-height: 1;
                display: inline-block;
                vertical-align: middle;
                margin-right: .2rem;
                margin-left: .2rem;
                font-size: .32rem;
                .icon-downarrow {
                    margin-left: 0.1rem;
                }
            }
        }
        .box-search {
            flex: 1;
            line-height: 1rem;
            .search-zone {
                height: .62rem;
                background-color: rgba(0,0,0,0.15);
                border-radius: .06rem;
                display: inline-block;
                width: 100%;
                vertical-align: middle;
                line-height: .62rem;
                font-size: .26rem;
                color: #68dbce;
                .icon-search {
                    color: @fontColor;
                    font-size: .28rem;
                    margin-left: .2rem;
                    margin-right: .01rem;
                }
            }
        }
        .nav-wrap-right {
            width: .94rem;
            font-size: .2rem;
            text-align: center;
            line-height: 1rem;
            a {
                line-height: 1;
                vertical-align: middle;
            }
            .text-icon {
                margin-bottom: .12rem;
                font-size: .4rem;
                display: block;
            }
        }
    }
</style>
