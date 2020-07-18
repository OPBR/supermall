<template>
  <div>
    <tab-bar>
      <tab-bar-item path="/home" active="blue">
        <div slot="item-text">首页</div>
        <img slot="item-icon" src="~assets/img/tabbar/home.svg" alt="">
        <img slot="item-icon-active" src="~assets/img/tabbar/home_active.svg" alt="">
      </tab-bar-item>
      <tab-bar-item path="/category">
        <div slot="item-text">分类</div>
        <img slot="item-icon" src="~assets/img/tabbar/category.svg" alt="">
        <img slot="item-icon-active" src="~assets/img/tabbar/category_active.svg" alt="">
      </tab-bar-item>
      <tab-bar-item path="/cart">
        <div slot="item-text">购物车</div>
        <img slot="item-icon" src="~assets/img/tabbar/cart.svg" alt="">
        <img slot="item-icon-active" src="~assets/img/tabbar/cart_active.svg" alt="">
      </tab-bar-item>
      <tab-bar-item path="/profile">
        <div slot="item-text">我的</div>
        <img slot="item-icon" src="~assets/img/tabbar/profile.svg" alt="">
        <img slot="item-icon-active" src="~assets/img/tabbar/profile_active.svg" alt="">
      </tab-bar-item>
    </tab-bar>
  </div>
</template>

<script>
import TabBar from 'components/common/tabbar/TabBar'
import TabBarItem from 'components/common/tabbar/TabBarItem'

export default {
  name: "MainTabBar",
  components: {
    TabBar,
    TabBarItem
  }
}
</script>