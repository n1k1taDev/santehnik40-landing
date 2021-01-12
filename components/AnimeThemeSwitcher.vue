<template>
  <div>
    <section>
      <svg
        id="darkMode"
        width="55"
        height="55"
        viewBox="0 0 55 55"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
        @click="toggleTheme"
      >
        <path
          class="sun"
          d="M55 27.5C55 42.6878 42.6878 55 27.5 55C12.3122 55 0 42.6878 0 27.5C0 12.3122 12.3122 0 27.5 0C42.6878 0 55 12.3122 55 27.5Z"
          fill="#FFBE18"
        />
      </svg>
    </section>
  </div>
</template>

<script>
import AnimeMinJs from '../assests/js/anime.min.js'

export default {
  components: { AnimeMinJs },
  data() {
    return {
      duration: 750,
      targets1: '.sun',
      targets2: '#darkMode',
    }
  },

  methods: {
    toggleTheme(AnimeMinJs) {
      const moonPath =
        'M14 27.5C14 42.6878 27.5 55 27.5 55C12.3122 55 0 42.6878 0 27.5C0 12.3122 12.3122 0 27.5 0C27.5 0 14 12.3122 14 27.5Z'
      const sunPath =
        'M55 27.5C55 42.6878 42.6878 55 27.5 55C12.3122 55 0 42.6878 0 27.5C0 12.3122 12.3122 0 27.5 0C42.6878 0 55 12.3122 55 27.5Z'
      const timeline = this.AnimeMinJs.timeline({
        duration: 750,
        easing: 'easeOutExpo',
      })
      let toggle = false
      timeline
        .add({ targets: '.sun', d: [{ value: toggle ? sunPath : moonPath }] })
        .add({ targets: '#darkMode', rotate: 320 }, '-= 350')

      this.$colorMode.preference =
        this.$colorMode.value === 'light' ? 'dark' : 'light'

      toggle = !toggle
    },
  },
}
</script>

<style>
svg {
  cursor: pointer;
}

body {
  font-family: sans-serif;
}
</style>
