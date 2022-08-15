 <template>
  <section id="contact">
    <div class="flex-wrap">
      <span class="small">Let's make it happen</span>
      <div class="email">
        <a class="a" href="mailto:hello@emblematic.co">
          <span>hello@emblematic.co</span>
        </a>
      </div>
    </div>
    <!-- <FooterIcon /> -->
  </section>
</template>

<script>
//import FooterIcon from "~/assets/icon.svg?inline";

export default {
  components: {
    //FooterIcon,
  },
};
</script>

<style lang="scss">
#contact {
  margin: 50vw 0 10vw 0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: relative;
  height: 80vh;

  .flex-wrap {
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 15px;
  }

  span.small {
    font-size: 4vw;
  }

  .email {
    width: auto;
  }

  a {
    font-size: 8vw;
    display: block;
    text-decoration: none;
    transition: all 0.35s ease-in-out;
    &:hover {
      transform: scale(1.04);
    }
  }

  &:before {
    z-index: -1;
    width: 100%;
    content: "";
    display: block;
    height: 65%;
    position: absolute;
    top: 20%;
    padding-bottom: 100vh;
    -webkit-transform: skewY(-4deg);
    -moz-transform: skewY(-4deg);
    -ms-transform: skewY(-4deg);
    -o-transform: skewY(-4deg);
    transform: skewY(-4deg);
    background-color: black;
  }
}
</style>