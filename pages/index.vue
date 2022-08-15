<template>
  <div>
    <section class="trigger">
      <div id="hero-container">
        <Logo />
        <h1 class="hero-text">
          <Typing />
        </h1>
      </div>
    </section>
    <Blacklogo />
    <Synopsis />
    <Technology />
    <Projects />
    <Contact />
    <Footer />
  </div>
</template>

<script>
import { gsap, ScrollTrigger, ExpoScaleEase } from "gsap/all";
export default {
  mounted() {
    gsap.registerPlugin(ScrollTrigger);
    //const tl = gsap.timeline({ delay: 0 });

    // ScrollTrigger.create({
    //   snap: 1 / 4, // snap whole page to the closest section!
    // });

    const tl = gsap
      .timeline({
        scrollTrigger: {
          trigger: ".trigger",
          scrub: 0.5,
          pin: true,
          start: "top",
          //end: "+=250%",
        },
      })
      .to(
        ".logo",
        {
          duration: 20,
          scale: 100,
          y: -1500,
          x: 3750,
          ease: ExpoScaleEase.config(1, 100),
          onComplete: () => turnWhite(this.$el.querySelector(".trigger")),
        },
        0
      )
      .to(
        ".hero-text",
        {
          duration: 10,
          y: "100",
          opacity: 0,
          ease: "power1.inOut",
          //stagger: { amount: 1 },
        },
        0
      )
      .to(
        "#technology",
        {
          duration: 1,
          y: -50,
          opacity: 1,
          ease: "power2.inOut",
        },
        0
      )
      .to(
        "#projects",
        {
          duration: 1,
          y: 50,
          opacity: 1,
          ease: "power2.inOut",
        },
        0
      )
      .to(
        ".logo-div",
        {
          delay: 10,
          duration: 5,
          opacity: 1,
          ease: "power1.inOut",
        },
        0
      )
      .to(
        ".black-logo",
        {
          delay: 10,
          x: 150,
          duration: 20,
          opacity: 1,
          ease: "power1.inOut",
          onReverseComplete: () =>
            turnBlack(this.$el.querySelector(".trigger")),
        },
        0
      )
      .to(
        ".projects-title",
        {
          y: 200,
          duration: 1,
          opacity: 1,
          ease: "power1.inOut",
        },
        0
      );
    // .to(".email", {
    //   //y: "-200",
    //   opacity: 1,
    //   scrollTrigger: {
    //     trigger: "#contact",
    //     scrub: true,
    //   },
    // });

    ScrollTrigger.batch(".synopsis-bg", {
      //start: "top-=350",
      onEnter: (batch) =>
        gsap.to(batch, {
          scale: 1.5,
          opacity: 1,
          y: 200,
          stagger: 1.25,
        }),
      onEnterBack: (batch) =>
        gsap.to(batch, {
          scale: 1.5,
          opacity: 1,
          y: 200,
          stagger: 1.25,
        }),
      onLeave: (batch) =>
        gsap.to(batch, {
          scale: 0.75,
          opacity: 0,
          y: -200,
        }),
      onLeaveBack: (batch) =>
        gsap.to(batch, {
          scale: 0.75,
          opacity: 0,
          y: -200,
        }),
    });

    ScrollTrigger.batch(".scroll-p", {
      ///start: "top-=350",
      onEnter: show,
      onLeave: hide,
      onEnterBack: show,
      onLeaveBack: hide,
    });

    ScrollTrigger.batch(".flex-item", {
      ///start: "top-=350",
      onEnter: show,
      onLeave: hide,
      onEnterBack: show,
      onLeaveBack: hide,
    });

    ScrollTrigger.batch(".video-link", {
      start: "top-=500",
      onEnter: (batch) =>
        gsap.to(batch, {
          opacity: 1,
          y: 200,
          stagger: 0.25,
        }),
      onLeaveBack: (batch) =>
        gsap.to(batch, {
          opacity: 0,
          y: -200,
        }),
    });
  },
};

function turnWhite(el) {
  el.classList.add("white");
}
function turnBlack(el) {
  el.classList.remove("white");
}
// Show the given batch
function show(batch) {
  batch.forEach((card, index) => {
    if (index % 2 == 0) {
      gsap.set(card, { opacity: 0, x: -250 });
    } else {
      gsap.set(card, { opacity: 0, x: 250 });
    }
    gsap.to(batch, {
      opacity: 1,
      x: 0,
      stagger: 0.15,
      overwrite: true,
      duration: 0.75,
    });
  });
}

// Hide the given batch
function hide(batch) {
  batch.forEach((card, index) => {
    if (index % 2 == 0) {
      gsap.set(card, { opacity: 0, x: 250, overwrite: true });
    } else {
      gsap.set(card, { opacity: 0, x: -250, overwrite: true });
    }
  });
}
</script>

<style lang="scss">
.hidden {
  display: none;
}
section {
  &.trigger {
    background: black;
  }
  width: 100vw;
  height: 100vh;
  overflow: hidden;

  // &:nth-of-type(2) {
  //   background: #eee;
  // }
  .logo {
    transition: opacity 1s ease-in;
  }

  &.white {
    background: white;
    .logo {
      //transition: opacity 1s ease-in-out;
      opacity: 0;
      visibility: hidden;
    }
  }
}

// .canvas-container {
//   margin: auto;
//   max-height: 1000px;
//   max-width: 1000px;
// }

h1.hero-text {
  letter-spacing: 0.25rem;
  //text-align: right;
  width: 80vw;
  position: relative;
  margin: 5vw 9vw 0 auto;
  font-size: clamp(1rem, 5vw, 2rem);
  color: #41b883;
}

body {
  overflow-x: hidden;
}
</style>
