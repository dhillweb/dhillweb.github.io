<script setup lang="ts">
const { onLoaded } = useScript('https://cdn.jsdelivr.net/particles.js/2.0.0/particles.min.js')

const onInitStars = () => {
  particlesJS('.particles-js', {
    particles: {
      number: {
        value: 500,
        density: {
          enable: true,
          value_area: 789.1476416322727,
        },
      },
      color: {
        value: '#ffffff',
      },
      shape: {
        type: 'star',
        stroke: {
          width: 0,
          color: '#000000',
        },
        polygon: {
          nb_sides: 5,
        },
      },
      opacity: {
        value: 0.2,
        random: false,
        anim: {
          enable: true,
          speed: 0.1,
          opacity_min: 0,
          sync: false,
        },
      },
      size: {
        value: 3,
        random: true,
        anim: {
          enable: true,
          speed: 2,
          size_min: 0,
          sync: false,
        },
      },
      line_linked: {
        enable: false,
        distance: 150,
        color: '#ffffff',
        opacity: 0.4,
        width: 1,
      },
      move: {
        enable: true,
        speed: 0.2,
        direction: 'none',
        random: true,
        straight: false,
        out_mode: 'out',
        bounce: false,
        attract: {
          enable: false,
          rotateX: 600,
          rotateY: 1200,
        },
      },
    },
    retina_detect: true,
  })
}

onLoaded(() => {
  nextTick(() => {
    onInitStars()
  })
})
</script>

<template>
  <div>
     
    <NuxtRouteAnnouncer />
    <NuxtWelcome />
    <!--
    <div class="particles-js"></div>
   -->
  </div>
</template>

<style scoped>
.particles-js {
  width: 100vw;
  height: 100vh;
  pointer-events: none;
}
</style>

