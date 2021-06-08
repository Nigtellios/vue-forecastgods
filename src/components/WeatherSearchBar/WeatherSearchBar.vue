<template>
  <div>

  </div>
</template>

<script>
import { onMounted, reactive, ref } from 'vue';

export default {
  name: 'WeatherSearchBar',
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

<style lang="scss" src="./WeatherSearchBar.scss" />
