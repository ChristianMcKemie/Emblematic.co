 <template>
  <section id="contact">
    <a class="email a" href="mailto:hello@emblematic.co"
      ><span>hello@emblematic.co</span></a
    >
  </section>
</template>

<style lang="scss">
#contact {
  margin-top: 20vw;
  display: flex;
  justify-content: center;
  align-items: center;

  a {
    //opacity: 0;
    font-size: 8vw;
    display: block;
    text-decoration: none;
     transition: all 0.35s ease-in-out;
    &:hover{
          transform: scale(1.04);
    }
  }
}
</style>