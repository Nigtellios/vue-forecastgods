<template>
  <div>
    <weather-board />

  </div>
</template>

<script>
import WeatherBoard from '@/components/WeatherBoard/WeatherBoard.vue';

export default {
  name: 'App',
  components: {
    WeatherBoard
  },
};
</script>
