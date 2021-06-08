<template>
  <div>
    <weather-hero-section />
    <weather-search-bar />
    Pick Location:
    <input v-model="query" />
    <button @click="fetchWeather">Get weather</button>

    <weather-card :weather="currentWeather" v-if="isWeatherLoaded" />
  </div>
</template>

<script>
import { onMounted, reactive, ref } from 'vue';
import axios from 'axios';
import WeatherCard from '@/components/WeatherCard/WeatherCard.vue';
import WeatherSearchBar from "@/components/WeatherSearchBar/WeatherSearchBar";
import WeatherHeroSection from "@/components/WeatherHeroSection/WeatherHeroSection";

export default {
  name: 'WeatherBoard',
  components: {
    WeatherSearchBar,
    WeatherHeroSection,
    WeatherCard,
  },
  setup() {
    let currentWeather = reactive({ });
    const query = ref('');

    const fetchWeather = async () => {
      try {
        const { data } = await axios.get(`http://api.weatherapi.com/v1/current.json?key=cb5a0c76682040ebb9e174737210106&q=${query.value}&aqi=no`)
        currentWeather = data;
        console.log(data)
      } catch(err) {
        console.error('Error:', err);
      }
    }

    const makeQuery = (event) => {
      console.log(event.target.value)
    }

    const isWeatherLoaded = () => {
      return Object.keys(currentWeather).length > 0;
    }
    
    onMounted(() => {
      // API CALL
      // fetchWeather();
    });

    return {
      currentWeather,
      query,
      fetchWeather,
      makeQuery,
      isWeatherLoaded,
    };
  },
};
</script>

<style lang="scss" src="./WeatherBoard.scss" />
