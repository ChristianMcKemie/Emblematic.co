<template>
  <div id="projects">
        <h2 class="projects-title"><span>WORK</span></h2>
    <div class="flex-wrapper">
      <a class="video-link a" target="_blank" href="//offthehookyachts.com">
        <video autoplay muted loop src="/OTH.mp4"></video>
      </a>
       <a class="video-link a" target="_blank" href="//cpa.morvilwebdev.com">
        <video autoplay muted loop src="/CPA.mp4"></video>
        </a>
      <a
        class="video-link a" target="_blank" href="//wilmingtoneyesurgerycenter.com">
        <video autoplay muted loop src="/WESC.mp4">
        </video>
        </a>
      <a class="video-link a" target="_blank" href="//americasmattress.com">
        <video autoplay muted loop src="/AM.mp4"></video></a>
      <a class="video-link a" target="_blank" href="//morris-coolideas.com">
        <video autoplay muted loop src="/MORRIS.mp4"></video>
        </a>
         <a class="video-link a" target="_blank" href="//morvil.com">
        <video autoplay muted loop src="/MORVIL.mp4"></video>
        </a>
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

  h2 {
    margin-top: -120px;
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
      transform: scale(1.1);
    }
  }
}

@media screen and (max-width: 800px) {
  .flex-wrapper {
    flex-direction: column;
  }
  .video-link {
    width: 100%;
  }
}
</style>