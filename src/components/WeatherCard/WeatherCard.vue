<template>
  <div>
    <p>xxdd</p>
  </div>
</template>

<script>

export default {
  name: 'WeatherCard',
  props: {
    weather: {
      type: Object,
      required: true,
    },
  },
  setup() {
 
  },
};
</script>

<style lang="scss" src="./WeatherCard.scss" />
