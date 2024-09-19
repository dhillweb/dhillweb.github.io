<template>
  <div>
    <NuxtParticles id="tsparticles" :options="options" @load="onLoad" />

    <section>
      <div class='air air1'></div>
      <div class='air air2'></div>
      <div class='air air3'></div>
      <div class='air air4'></div>
    </section>


  </div>
</template>

<script setup lang="ts">

import type { Container } from 'tsparticles'

const options = {
  fullScreen: {
    enable: true,
    zIndex: -10
  },
  background: {
    color: ""
  },
  interactivity: {
    events: {
      onClick: {
        enable: true,
        mode: "repulse"
      },
      onHover: {
        enable: true,
        mode: "bubble"
      }
    },
    modes: {
      bubble: {
        distance: 200,
        duration: 2,
        opacity: 0,
        size: 0,
        speed: 3
      },
      repulse: {
        distance: 400,
        duration: 0.4
      }
    }
  },
  particles: {
    color: { value: "#ffffff" },
    move: {
      direction: "none",
      enable: true,
      outModes: "out",
      random: true,
      speed: 0.3
    },
    number: {
      density: {
        enable: true
      },
      value: 600
    },
    opacity: {
      animation: {
        enable: true,
        speed: 5
      },
      value: { min: 0.3, max: 0.6 }
    },
    shape: {
      type: "circle"
    },
    size: {
      value: 1
    }
  }
}

const onLoad = (container: Container) => {
  // Do something with the container
  container.pause()
  setTimeout(() => container.play(), 2000)
}
</script>
<style>
body {
  margin: 0;
  background-color: black;
}

h1 {
  color: aliceblue;
  text-align: center;
  top: 50%;
  left: 50%;
  position: absolute;
}

section {
  position: relative;
  width: 100%;
  height: 100vh;
  overflow: hidden;
}

section .air {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 100px;
  background: url(/wave.png);
  background-size: 1000px 100px
}

section .air.air1 {
  animation: wave 30s linear infinite;
  z-index: 1000;
  opacity: 1;
  animation-delay: 0s;
  bottom: 0;
}

section .air.air2 {
  animation: wave2 15s linear infinite;
  z-index: 999;
  opacity: 0.5;
  animation-delay: -5s;
  bottom: 10px;
}

section .air.air3 {
  animation: wave 30s linear infinite;
  z-index: 998;
  opacity: 0.2;
  animation-delay: -2s;
  bottom: 15px;
}

section .air.air4 {
  animation: wave2 5s linear infinite;
  z-index: 997;
  opacity: 0.7;
  animation-delay: -5s;
  bottom: 20px;
}

@keyframes wave {
  0% {
    background-position-x: 1px;
  }

  100% {
    background-position-x: 1000px;
  }
}

@keyframes wave2 {
  0% {
    background-position-x: 1px;
  }

  100% {
    background-position-x: -1000px;
  }
}
</style>
