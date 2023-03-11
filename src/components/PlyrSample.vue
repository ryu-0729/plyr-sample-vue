<template>
  <video
    id="player"
    class="video"
    ref="video"
    controls
    crossorigin
    playsinline
    data-poster="https://cdn.plyr.io/static/demo/View_From_A_Blue_Moon_Trailer-HD.jpg"
  >
    <source
      src="https://cdn.plyr.io/static/demo/View_From_A_Blue_Moon_Trailer-720p.mp4"
      type="video/mp4"
    />
  </video>
</template>

<script>
import Plyr from "plyr";

export default {
  name: "PlyrSample",
  mounted() {
    new Plyr("#player", {
      debug: true,
      title: "View From A Blue Moon",
      keyboard: {
        global: true,
      },
      tooltips: {
        controls: true,
      },
      captions: {
        active: true,
      },
      vimeo: {
        // Prevent Vimeo blocking plyr.io demo site
        referrerPolicy: "no-referrer",
      },
      mediaMetadata: {
        title: "View From A Blue Moon",
        album: "Sports",
        artist: "Brainfarm",
        artwork: [
          {
            src: "https://cdn.plyr.io/static/demo/View_From_A_Blue_Moon_Trailer-HD.jpg",
            type: "image/jpeg",
          },
        ],
      },
      markers: {
        enabled: true,
        points: [
          {
            time: 40,
            label: "first marker",
          },
          {
            time: 80,
            label: "second marker",
          },
          {
            time: 90,
            label: "<div class='color'>third</div>",
          },
        ],
      },
    });
  },
};
</script>

<style>
.color {
  background-color: red;
}
</style>
