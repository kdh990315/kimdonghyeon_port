<template>
  <router-view></router-view>
</template>

<script>
import Lenis from '@studio-freight/lenis'

export default {
  mounted: function () {
    this.scrollAnimation();
  },
  methods: {
    scrollAnimation() {
      const lenis = new Lenis({
        duration: 3,
        easing: (t) => Math.min(1, 1.001 - Math.pow(2, -10 * t))
      })

      function raf(time) {
        lenis.raf(time)
        requestAnimationFrame(raf)
      }

      requestAnimationFrame(raf)
    }
  }
}
</script>

<style lang="scss">
@import "@/scss/reset.scss";

body {
  background-color: #313030;
  overflow-x: hidden;
}
</style>
