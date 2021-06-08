<!-- This is basically legacy Vue 2 Component file -->
<template>
  <div>
    <p>{{ title }} - {{infoResponse}} {{ currentW }}</p>
  </div>
</template>

<script>

export default {
  name: 'WeatherHeroSection',
  data() {
    return {
      title: 'Forecast Gods',
      infoResponse: `Current temperature (in Celsius) is: `,
      currentW: 32,
    }
  },
};

</script>

<style lang="scss" src="./WeatherHeroSection.scss" />
