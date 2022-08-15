 <template>
  <footer id="footer">
    <div class="flex-wrap">
      <div class="left">
        <GreenLogo />
        <span class="copy"
          ><span> ©︎ Future Formed Inc {{ year }}</span>
        </span>
      </div>
      <div class="right">
        <span>2101 Medeira Ct<br />Wilmington NC 28405</span>
        <a class="a mail" href="mailto:hello@emblematic.co">
          <span>hello@emblematic.co</span>
        </a>
        <a class="a phone" href="tel:+19106160694">
          <span>910.616.0694</span>
        </a>
      </div>
    </div>
  </footer>
</template>

<script>
import GreenLogo from "~/assets/greenlogo.svg?inline";
let year = new Date().getFullYear();
export default {
  components: {
    GreenLogo,
  },
  data() {
    return {
      year: year,
    };
  },
};
</script>

<style lang="scss">
#footer {
  border-top: 3px double rgb(60, 60, 60);
  background: black;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: relative;
  margin-top: -30vh;
  min-height: 30vh;
  @media screen and (max-width: 900px) {
    min-height: 50vh;
  }
  width: 100vw;

  #green-logo {
    width: 100%;
    max-width: 250px;
  }

  .mail,
  .phone,
  .copy {
    span {
      color: white;
    }
  }

  .flex-wrap {
    width: 80vw;
    height: 100%;
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    z-index: 1;
    gap: 15px;
    flex-wrap: wrap;
    @media screen and (max-width: 900px) {
      align-items: flex-start;
      gap: 10vw;
      flex-direction: column;
    }
  }

  .left,
  .right {
    min-width: 300px;
    gap: 15px;
    width: 30%;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    height: 100%;
  }

  .copy {
    font-size: clamp(0.8rem, 3vw, 1.2rem);
    justify-self: flex-end;
  }

  a {
    font-size: 1rem;
    display: block;
    text-decoration: none;
    transition: all 0.35s ease-in-out;
    &:hover {
      transform: scale(1.04);
    }
  }
}
</style>