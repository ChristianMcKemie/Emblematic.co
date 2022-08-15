<template>
  <div id="technology">
    <h2 class="projects-title"><span>Tools we use</span></h2>
    <div class="flex-wrap">
      <div class="flex-item">
        <NodeLogo />
      </div>
      <div class="flex-item">
        <ReactLogo />
      </div>
      <div class="flex-item">
        <SaleorLogo />
      </div>
      <div class="flex-item">
        <WordpressLogo />
      </div>
      <div class="flex-item">
        <VueLogo />
      </div>
      <div class="flex-item">
        <GSAPLogo />
      </div>
      <div class="flex-item">
        <ShopifyLogo />
      </div>
    </div>
  </div>
</template>

<script>
import NodeLogo from "~/assets/Node.js_logo.svg?inline";
import ReactLogo from "~/assets/React.js_logo.svg?inline";
import SaleorLogo from "~/assets/Saleor.logo.svg?inline";
import WordpressLogo from "~/assets/Wordpress.logo.svg?inline";
import VueLogo from "~/assets/Vue.js_logo.svg?inline";
import GSAPLogo from "~/assets/gsap-greensock.svg?inline";
import ShopifyLogo from "~/assets/Shopify.logo.svg?inline";

export default {
  components: {
    NodeLogo,
    ReactLogo,
    SaleorLogo,
    WordpressLogo,
    VueLogo,
    GSAPLogo,
    ShopifyLogo,
  },
};
</script>

<style lang="scss">
#technology {
  //padding-top: 12vw;
  opacity: 0;

  margin: 0 5vw;
  width: 90vw;

  h2 {
    margin-bottom: 230px;
  }
}
.flex-wrap {
  gap: 5vw;
  flex-wrap: wrap;
  @media screen and (max-width: 800px) {
    gap: 70px;
  }
}
.flex-wrap,
.flex-item {
  display: flex;
  justify-content: center;
  align-items: center;
}
.flex-item {
  opacity: 0;
  max-width: 20vw;
  @media screen and (max-width: 800px) {
    max-width: 60vw;
  }

  svg{
    height:100%;
    width:100%;
  }
}
</style>