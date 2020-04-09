<template>
  <tab-bar>
    <Tab-bar-item path="/home">
      <img slot="item-icon" src="../../assets/img/tabbar/home.svg" alt="">
      <img slot="item-icon-active" src="../../assets/img/tabbar/home-active.svg" alt="">
      <div slot="item-text">首页</div>
    </Tab-bar-item>
    <Tab-bar-item path="/category">
      <img slot="item-icon" src="../../assets/img/tabbar/category.svg" alt="">
      <img slot="item-icon-active" src="../../assets/img/tabbar/category-active.svg" alt="">
      <div slot="item-text">分类</div>
    </Tab-bar-item>
    <Tab-bar-item path="/cart">
      <img slot="item-icon" src="../../assets/img/tabbar/cart.svg" alt="">
      <img slot="item-icon-active" src="../../assets/img/tabbar/cart-active.svg" alt="">
      <div slot="item-text">购物车</div>
    </Tab-bar-item>
    <Tab-bar-item path="/profile">
      <img slot="item-icon" src="../../assets/img/tabbar/profile.svg" alt="">
      <img slot="item-icon-active" src="../../assets/img/tabbar/profile-active.svg" alt="">
      <div slot="item-text">我的</div>
    </Tab-bar-item>
  </tab-bar>
</template>

<script>
  import TabBar from '../../components/common/tabbar/TabBar'
  import TabBarItem from '../../components/common/tabbar/TabBarItem'
  export default {
    name: "MainTabBar",
    components:{
      TabBar,
      TabBarItem
    }
  }
</script>

<style scoped>

</style>
