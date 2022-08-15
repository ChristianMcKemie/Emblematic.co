<template>
  <div class="progress-bar">
    <div class="filled-bar" :style="widthStyle"></div>
  </div>
</template>

<script>
export default {
  props: {
    value: {
      type: Number,
      default: 0,
    },
  },
  data() {
    return {
      width: this.value,
    };
  },
  created() {
    if (process.browser) {
      window.addEventListener("scroll", this.handleScroll);
    }
  },
  methods: {
    handleScroll() {
      let scrollTop = window.scrollY;
      let docHeight = document.body.offsetHeight;
      let winHeight = window.innerHeight;
      let scrollPercent = scrollTop / (docHeight - winHeight);
      this.width = (scrollPercent * 100).toFixed(2);
      return scrollPercent;
    },
  },
  computed: {
    widthStyle() {
      return {
        width: this.width + "%",
      };
    },
  },
};
</script>

<style scoped>
.progress-bar {
  top: 0;
  position: fixed;
  height: 4px;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  z-index: 2;
}

.filled-bar {
  transition: width 1s ease;
  position: absolute;
  top: 0;
  left: 0;
  z-index: 2;
  height: 100%;
  width: 0;
  background: #019457;
}
</style>
