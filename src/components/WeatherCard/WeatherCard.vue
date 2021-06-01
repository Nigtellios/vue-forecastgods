<template>
  <div>
    xxdd
  </div>
</template>

<script>
import { onMounted, reactive, ref } from 'vue';

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
