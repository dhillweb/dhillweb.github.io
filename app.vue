<template>
  <div>
    <NuxtParticles id="tsparticles" :options="options" @load="onLoad" />
    <!-- <div style="height: 10rem; width: 30rem; background-color: chocolate; margin-left: auto; margin-right: auto;">
    </div> -->
  </div>
</template>

<script setup lang="ts">

import type { ISourceOptions, Container } from "@tsparticles/engine";

const options: ISourceOptions = {
  fpsLimit: 120,
  particles: {
    color: {
      value: ["#BE1F00", "#14000A", "#FF009A", "#BDE8FF", "#5C4991"]
    },
    number: {
      value: 50
    },
    shape: {
      type: "circle"
    },
    opacity: {
      value: 1
    },
    size: {
      value: 400
    },
    move: {
      enable: true,
      speed: 10,
    }
  },
  style: {
    filter: "blur(100px)"
  },
  detectRetina: true,
}

const onLoad = (container: Container) => {
  // Do something with the container
  container.pause()
  setTimeout(() => container.play(), 2000)
}
</script>
<style>
#tsparticles {
  position: fixed;
  width: 100vw;
  height: 100vw;
  z-index: -10;
}
</style>