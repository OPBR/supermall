<template>
  <div class="wrapper" ref="wrapper">
    <div class="content">
      <slot></slot>
    </div>
  </div>
</template>

<script>
import BScroll from "better-scroll";

export default {
  name: "Scroll",
  props: {
    probeType: {
      type: Number,
      default() {
        return 0;
      }
    },
    pullUpload: {
      type: Boolean,
      default() {
        return false;
      }
    }
  },
  data() {
    return {
      scroll: null
    };
  },
  mounted() {
    // setTimeout(() => {

    // }, 3000)
    // 1. 创建BScroll对象
    this.scroll = new BScroll(this.$refs.wrapper, {
      click: true,
      probeType: this.probeType,
      pullUpLoad: this.pullUpload
    });

    // 2. 监听滚动的位置
    this.scroll.on("scroll", position => {
      this.$emit("scroll", position);
    });

    // 3. 监听上拉事件
    this.scroll.on("pullingUp", () => {
      this.$emit("pullingUp")
    });
  },
  methods: {
    scrollTo(x, y, time) {
      this.scroll && this.scroll.scrollTo(x, y, time);
    },
    finishPullUp() {
      this.scroll && this.scroll.finishPullUp()
    },
    refresh() {
      this.scroll && this.scroll.refresh()
    }
  }
};
</script>