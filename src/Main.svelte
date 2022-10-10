<script>
  import { onMount } from "svelte";
  import { hotspots, page_num } from "./store";
  let audio = null;

  // https://image-map.weebly.com/
  // Create and export image maps from the above site

  console.log($hotspots);

  onMount(() => {
    _gorilla.addEventListener(
      "mousedown",
      function () {
        play("gorilla");
      },
      false
    );
    _stop.addEventListener(
      "mousedown",
      function () {
        play("stop");
      },
      false
    );
    _monkey.addEventListener(
      "mousedown",
      function () {
        play("monkey");
      },
      false
    );
    _peach.addEventListener(
      "mousedown",
      function () {
        play("peach");
      },
      false
    );
    _ring.addEventListener(
      "mousedown",
      function () {
        play("ring");
      },
      false
    );
    _frog.addEventListener(
      "mousedown",
      function () {
        play("frog");
      },
      false
    );
    _drum.addEventListener(
      "mousedown",
      function () {
        play("drum");
      },
      false
    );
  });

  // go.addEventListener('mouseout', stop, false);

  //   function p_gorilla() {
  //     audio = new Audio("./assets/audio/gorilla.mp3");
  //     if (audio.paused) {
  //       audio.play();
  //     }
  //   }

  function play(item) {
    audio = new Audio(`./assets/audio/${item}.mp3`);
    console.log(audio);
    audio.play();
  }

  let _frog, _drum, _ring, _stop, _peach, _monkey, _gorilla;
</script>

<div class="imgbox">
  <img
    class="center-fit"
    src="./assets/png/phonics_1_5.png"
    id="map-image"
    alt=""
    usemap="#map"
  />

  <map name="map">
    <area
      bind:this={_frog}
      shape="rect"
      coords="432, 589, 628, 814"
      title="frog"
      alt=""
      tabindex="0"
    />
    <area
      bind:this={_drum}
      shape="rect"
      coords="115, 589, 311, 815"
      title="drum"
      alt=""
      tabindex="0"
    />
    <area
      bind:this={_ring}
      shape="rect"
      coords="431, 339, 628, 568"
      title="ring"
      alt=""
      tabindex="0"
    />
    <area
      bind:this={_stop}
      shape="rect"
      coords="111, 345, 311, 568"
      title="stop"
      alt=""
      tabindex="0"
    />
    <area
      bind:this={_peach}
      shape="rect"
      coords="481, 111, 688, 314"
      title="peach"
      alt=""
      tabindex="0"
    />
    <area
      bind:this={_monkey}
      shape="rect"
      coords="246, 109, 462, 314"
      title="monkey"
      alt=""
      tabindex="0"
    />
    <area
      bind:this={_gorilla}
      shape="rect"
      coords="23, 107, 227, 314"
      title="gorilla"
      alt=""
      tabindex="0"
    />
  </map>
</div>

<style>
  * {
    margin: 0;
    padding: 0;
  }
  .imgbox {
    display: grid;
    height: 100%;
  }
  .center-fit {
    grid-area: 1/1;
    max-width: 100%;
    max-height: 100vh;
    margin: auto;
    z-index: 0;
  }
</style>
