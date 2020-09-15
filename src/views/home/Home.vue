<template>
  <div class="home">

  	<navbar class='home-navbar'>
  		<div slot='center'>桃饱网</div>
  	</navbar>
		
    <scroll class="content"
            ref="scroll"
            :probe-type="3"
            :pull-up-load="true"
            >
      <home-swiper :swiper='swiper'></home-swiper>

      <home-recommentd :recommentd='recommentd'></home-recommentd>

      <tab-control :titles="['流行','新款','精选']"
       class='tab-control'
      @tabClick='tabClick'
       >

      </tab-control>

      <goods-list :goods="goods[currentType].list" class='goods-list'></goods-list>

    </scroll>  
		
  </div>
</template>

<script>
import Navbar from 'common/navbar/Navbar';
import HomeSwiper from 'views/home/homeswiper/HomeSwiper';
import HomeRecommentd from 'views/home/homerecommentd/HomeRecommentd'; 
import Scroll from 'common/scroll/Scroll'

import GoodsList from 'components/content/goods/GoodsList';
import TabControl from 'components/content/tabcontrol/TabControl';

import BScroll from 'better-scroll'

export default {
  name: 'Home',
  components: {
 	Navbar,HomeSwiper,HomeRecommentd,TabControl,GoodsList,Scroll
  },
  created(){
  },
  activated() {
    this.$refs.scroll.scrollTo(0, this.saveY, 0)
    this.$refs.scroll.refresh()
  },
  deactivated() {
    this.saveY = this.$refs.scroll.getScrollY()
  },
  mounted() {
  },
  data(){
  	return{
  		swiper:[
  			{link:'baidu.com',href:'http://localhost/xiaoxianyu/image/swiper/0.jpg'},
  			{link:'baidu.com',href:'http://localhost/xiaoxianyu/image/swiper/1.jpg'},
  			{link:'baidu.com',href:'http://localhost/xiaoxianyu/image/swiper/2.jpg'},
  			{link:'baidu.com',href:'http://localhost/xiaoxianyu/image/swiper/3.jpg'},
  		],
  		recommentd:[
  			{link:'',href:'http://localhost/xiaoxianyu/image/recommentd/眼影.jpg',title:'靓丽眼影'},
  			{link:'',href:'http://localhost/xiaoxianyu/image/recommentd/口红.jpg',title:'精致口红'},
  			{link:'',href:'http://localhost/xiaoxianyu/image/recommentd/蜜粉.jpg',title:'粉饼蜜粉'},
  			{link:'',href:'http://localhost/xiaoxianyu/image/recommentd/笔刷.jpg',title:'工具笔刷'}
  		],
      goods:{
        'pop' :{
          page: 0, 
          list:[
            {imgsrc:'https://gaitaobao1.alicdn.com/tfscom/i3/2200869404234/O1CN01gJVDzr1h9DY7GE4ee_!!0-item_pic.jpg_240x240xz.jpg_.webp',title:'三月兔/Marchare 樱花粉扑美妆蛋不吃粉海绵化妆蛋粉扑',price:'29.9',cfav:'1200'},
            {imgsrc:'https://gaitaobao2.alicdn.com/tfscom/i4/2307829976/O1CN01dRcRQI2NZ3l9rZzP0_!!2307829976-0-lubanu-s.jpg_240x240xz.jpg_.webp',title:'卡姿兰彩妆套装初学者化妆品全套组合淡妆自然学生灰姑娘套装正品',price:'169.9',cfav:'1104'},
            {imgsrc:'https://img.alicdn.com/bao/uploaded/i1/810921128/O1CN012H8qbg1KCfMwdpQJv_!!810921128-0-lubanu-s.jpg_468x468q75.jpg_.webp',title:'Nico粉饼定妆粉散粉干粉控油持久遮瑕防水干湿两用修容蜜粉女正品券35元¥14.90¥49.9nico旗舰店月销 1.99万',price:'14.9',cfav:'199'},
            {imgsrc:'https://img.alicdn.com/bao/uploaded/i1/784497909/O1CN01wrifMQ28IN4VK1ec0_!!0-item_pic.jpg_468x468q75.jpg_.webp',title:'唇刷口红笔刷伸缩便携带盖化妆刷女一支装初学者遮瑕刷迷你眼影刷券5元¥7.90¥12.9zoreya旗舰店月销 6024',price:'7.9',cfav:'62'},
            {imgsrc:'https://img.alicdn.com/bao/uploaded/i3/123601316/TB20u_4g8jTBKNjSZFwXXcG4XXa_!!123601316.jpg_468x468q75.jpg_.webp',title:'简大小姐貂毛平头唇刷化妆师专用伸缩便携款唇膏刷口红刷女化妆刷¥36¥75简 大小姐月销 1554',price:'36.9',cfav:'1554'},
            {imgsrc:'https://img.alicdn.com/bao/uploaded/i1/2457188379/O1CN01Bv9RKz2BldF5ZKSi7_!!2457188379-0-lubanu-s.jpg_468x468q75.jpg_.webp',title:'丽扬散粉空气蜜粉定妆粉女控油持久遮瑕提亮肤色防水网红修容粉¥30¥98丽扬化妆品旗舰店月销 8588',price:'59.0',cfav:'3359'},
            {imgsrc:'https://img.alicdn.com/bao/uploaded/i3/191008125/O1CN01Tq24PO29tIdvrlYqx_!!191008125-0-lubanu-s.jpg_468x468q75.jpg_.webp',title:'美康粉黛旷野玫瑰散粉定妆粉饼女持久控油防水防汗不易脱妆蜜粉¥49¥89美康粉黛旗舰店月销 11.80万',price:'49.9',cfav:'1180'},
            {imgsrc:'https://gaitaobao2.alicdn.com/tfscom/i3/1773211220/O1CN01y9xLtJ1KsnoAPMNuy_!!0-item_pic.jpg_240x240xz.jpg_.webp',title:'ZEESEA滋色妆前乳隔离霜保湿遮瑕液粉底液定妆粉散粉3件彩妆套装',price:'129.9',cfav:'1069'},
            
          ]
        },
        'news':{
          page: 0, 
          list:[]
        },
        'sell':{
          page: 0, 
          list:[]},
      } ,
      currentType:'pop',
      saveY: 0
  	}
  },
  methods:{
    // 事件监听
    tabClick(index){
      switch(index){
        case 0:
        this.currentType='pop'
        break
        case 1:
        this.currentType='news'
        break
        case 2:
        this.currentType='sell'
        break
      }
    },
  }
};
</script>

<style scoped>
	.home{
		margin-top: 44px;

	}
	.home-navbar{
		position: fixed;
		top:0px;
		left: 0px;
		width: 100%;
		z-index: 1;
		background-color:rgb(255, 181, 206);
		box-shadow: 0,1px,1px,rgba(0,0,0,.05);
	}
	.tab-control{
		position: sticky;
		top:44px;
    z-index:9;
	}
  .content {
    overflow: hidden;
    position: absolute;
    top: 44px;
    bottom: 49px;
    left: 0;
    right: 0;
  }
</style>