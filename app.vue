<template>
  <div>
    <NuxtParticles id="tsparticles" :options="options" @load="onLoad" />


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
    color: "#000"
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
    color: { value: "#fff" },
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
