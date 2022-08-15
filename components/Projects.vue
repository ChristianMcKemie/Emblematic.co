<template>
  <div id="projects">
    <h2 class="projects-title"><span>Past work</span></h2>
    <div class="flex-wrapper">
      <a class="video-link a" target="_blank" href="//offthehookyachts.com">
        <video autoplay muted loop src="/OTH.mp4"></video>
      </a>
      <a class="video-link a" target="_blank" href="//culturesync.net">
        <video autoplay muted loop src="/CULTURESYNC.mp4"></video>
      </a>
      <a class="video-link a" target="_blank" href="//www.hi-float.com">
        <video autoplay muted loop src="/HIFLOAT.mp4"></video>
      </a>
      <a class="video-link a" target="_blank" href="//americasmattress.com">
        <video autoplay muted loop src="/AM.mp4"></video
      ></a>
      <!-- <a class="video-link a" target="_blank" href="//cpa.morvilwebdev.com">
        <video autoplay muted loop src="/CPA.mp4"></video>
      </a> -->
      <!-- <a
        class="video-link a"
        target="_blank"
        href="//wilmingtoneyesurgerycenter.com"
      >
        <video autoplay muted loop src="/WESC.mp4"></video>
      </a> -->
      <!-- <a class="video-link a" target="_blank" href="//morris-coolideas.com">
        <video autoplay muted loop src="/MORRIS.mp4"></video>
      </a> -->
    </div>
  </div>
</template>

<style lang="scss">
#projects {
  //padding-bottom: 30%;
  //padding-top: 15%;
  //@media screen and (max-width: 800px) {
  //padding-top: 20%;
  //}
  width: 100%;
  display: block;
  opacity: 0;
  width: 92vw;
  margin: 0 4vw;
  padding-top: 10vw;
  padding-bottom: 50vh;

  h2 {
    margin-bottom: 100px;
  }
}
.flex-wrapper {
  display: flex;
  gap: 4vw;
  flex-wrap: wrap;
  justify-content: space-evenly;
  padding: 0;
}
.video-link {
  opacity: 0;
  width: calc(50% - 2vw);

  video {
    border-radius: 5px;
    width: 100%;
    transition: 0.35s all ease-in-out;
    &:hover {
      border: 10px double #41b883;
      transform: rotate3d(-0.01, -0.01, 0, -20deg);
    }
  }
  &:nth-of-type(even) {
    video:hover {
      transform: rotate3d(0.01, 0.01, 0, 20deg);
    }
  }
}

@media screen and (max-width: 800px) {
  .flex-wrapper {
    flex-direction: column;
    gap: 10vw;
  }
  .video-link {
    width: 90%;
    margin: 0 5%;
  }
}
</style>