<template>
  <div>
    <NuxtParticles id="tsparticles" :options="options" />
    <div class="wrapper">
      <div class="card">

      </div>
    </div>
  </div>
</template>

<script setup lang="ts">

const options = {

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
    filter: "blur(150px)"
  },
  detectRetina: true,
}

const updateParticleNumber = () => {
  if (import.meta.client) {
    const particleNumber = window.innerWidth < 640 ? 60 : 120;
    options.particles.number.value = particleNumber;
  }
}
if (import.meta.client) {
  window.addEventListener("resize", updateParticleNumber);
  updateParticleNumber();
}
</script>
<style>
#tsparticles {
  position: fixed;
  z-index: -10;
}

body {
  margin: 0;
}
</style>