<template>
  <div id="home">
    <nav-bar class="home-nav">
      <div slot="center">VueMarket</div>
    </nav-bar>
    <home-swiper :cbanners="banners"></home-swiper>
    <home-recommend :crecommends="recommends"></home-recommend>
    <home-feature></home-feature>
    <tab-control :titles="['流行','新款','精选']"></tab-control>
    <ul>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
      <li>less</li>
    </ul>
  </div>
</template>

<script>
  import NavBar from '../../components/common/navbar/NavBar'
  import {
    getHomeMultiData,
    getGoodsData
  } from "../../network/home";
  import HomeSwiper from './childcomps/HomeSwiper';
  import HomeRecommend from './childcomps/HomeRecommend';
  import HomeFeature from './childcomps/HomeFeature';

  import TabControl from '../../components/content/tabcontrol/TabControl'

  export default {
    name: "Home",
    components:{
      NavBar,
      HomeSwiper,
      HomeRecommend,
      HomeFeature,
      TabControl
    },
    data() {
      return {
        result:null,
        banners:[],
        recommends:[],
        goods:{
          'pop': {page: 0,list: []},
          'new': {page: 0,list: []},
          'sell': {page: 0,list: []},
        }
      }
    },
    created() {
      //1.请求多个数据
      this.getHomeMultiData()

      //请求商品数据
      this.getGoodsData('pop');
      this.getGoodsData('new');
      this.getGoodsData('sell');
    },
    methods: {
      getHomeMultiData(){
        getHomeMultiData().then(res => {
          // console.log(res);
          this.result = res
          this.banners = res.data.banner.list;
          this.recommends = res.data.recommend.list;
        })
      },
      getGoodsData(type){
        const page = this.goods[type].page + 1
        getGoodsData(type,page).then(res => {
          console.log(res);
          this.goods[type].list.push(...res.data.list)
          this.goods[type].page += 1
        })
      }
    }
  }
</script>

<style scoped>
  #home {
    padding-top: 44px;
  }
  .home-nav {
    background-color: var(--color-tint);
    color: #fff;

    position: fixed;
    left: 0;
    top: 0;
    right: 0;
    z-index: 9;
  }
</style>
