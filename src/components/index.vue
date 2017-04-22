<template>
    <div>
      <!--头部-->
      <nHeader/>
      <!--中间广告位-->
      <a class="ap-block" href="#">
          <img src="http://p1.meituan.net/mmc/dbc70b32f22415bc55d1523d7141735c18365.jpg" alt="">
      </a>
      <!--中间的菜单按钮-->
      <Carousel/>
      <div class="reverse-gap"></div>
      <ShopGuide/>
      <div class="reverse-gap"></div>
      <List/>
      <a href="#" class="view-more text-blue">查看全部团购</a>
      <Footer></Footer>
    </div>
</template>

<script>
import nHeader from './header/header.vue'
import Carousel from './carousel/carousel.vue'
import ShopGuide from './pageComponent/indexPage/shopGuide.vue'
import List from './list/list.vue'
import Footer from './footer/footer.vue'

export default {
  name: 'index',
  data () {
    return {
      msg: ''
    }
  },
  components: {
    nHeader,
    Carousel,
    ShopGuide,
    List,
    Footer
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less" rel="stylesheet/less">
.ap-block {
    display: block;
    img {
      width: 100%;
    }
}
.view-more{
    display: block;
    height: .8rem;
    line-height: .8rem;
    font-size: .3rem;
    position: relative;
    background-color: #fff;
    padding-left: .2rem;
    border-bottom: 1px solid #DDD8CE;
    &:after{
      position: absolute;
      right: .25rem;
      top: 50%;
      display: block;
      content: '';
      width: .6em;
      height: .6em;
      border-left: .04rem solid #06c1ae;
      border-bottom: .04rem solid #06c1ae;
      transform: translateY(-50%) scaleY(0.7) rotateZ(-135deg);
    }
}
</style>
