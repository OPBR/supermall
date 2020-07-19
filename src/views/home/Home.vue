<template>
  <div id="home">
    <nav-bar class="home-nav">
      <div slot="center">购物街</div>
    </nav-bar>
    <home-swiper :banners="banners"></home-swiper>
    <home-recommend-view :recommends="recommends"></home-recommend-view>
    <home-feature-view></home-feature-view>
  </div>
</template>

<script>
import NavBar from "components/common/navbar/NavBar";
import HomeSwiper from "./childComps/HomeSwiper";
import HomeRecommendView from './childComps/HomeRecommendView'
import HomeFeatureView from './childComps/HomeFeatureView'

import { getHomeMultidata } from "network/home.js";

export default {
  name: "Home",
  components: {
    NavBar,
    HomeSwiper,
    HomeRecommendView,
    HomeFeatureView
  },
  data() {
    return {
      banners: [],
      recommends: []
    };
  },
  created() {
    getHomeMultidata().then(res => {
      console.log(res);
      this.banners = res.data.banner.list;
      this.recommends = res.data.recommend.list;
    });
  }
};
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
  right: 0;
  top: 0;

  z-index: 9;
}
/* .love {
  width: 100%;
  height: 100px;
  color: pink;
  font-weight: 700;
  font-size: 44px;
  text-align: center;
  margin-top: 200px;
} */
</style>