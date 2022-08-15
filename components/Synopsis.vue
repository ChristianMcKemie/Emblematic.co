 <template>
  <section id="synopsis">
    <div class="synopsis-bg">
      <span>
        <p class="scroll-p">
          We're a small team of designers and developers passionate about
          building on the edge of what's possible.
        </p>
        <br />
        <p class="scroll-p white">
          Let's create the next generation in your companies digital future.
        </p>
      </span>
    </div>
  </section>
</template>

<style lang="scss">
#synopsis div {
  font-size: 2.3rem;
  background: black;
  max-width: 60vw;
  padding: 5vw;
  margin: auto;
  max-height: auto;
  border-radius: 5px;
  @media screen and (max-width: 800px) {
    padding: 7.5vw 5vw;
    font-size: 1.2rem;
  }

  p.white {
    color: white;
  }
}
</style>