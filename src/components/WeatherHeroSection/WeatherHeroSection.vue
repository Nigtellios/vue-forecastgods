<!-- This is basically legacy Vue 2 Component file -->
<template>

  <div class="hero">
    <a class="hero__button" @click="currentW++">{{ buttonContentIncrease }}</a>
    <a class="hero__button" @click="currentW--">{{ buttonContentDecrease }}</a>
  </div>

  <div class="hero-bottom">
    <!-- Some Functionality testing -->
    <p>{{ title }} - {{infoResponse}} {{ currentW }}</p>
    <p @click="titleToChange = `Very nice ${userName}!`">Change this one: {{ titleToChange }}</p>
    <p @click="changeTitle">Try this one instead: {{ titleToChange }}</p>
  </div>

  <div v-if="showSubBottom" class="hero-sub-bottom">
    <!-- Conditional Rendering Test -->
    <p>This is generated dynamically based on v-if condition.</p>
    <p>{{ title }} - {{infoResponse}} {{ currentW }}</p>
  </div>

  <div v-else class="hero-sub-bottom">
    <!-- Conditional Rendering Test -->
    <p>This is else condition in Vue.</p>
  </div>

</template>

<script>

export default {
  name: 'WeatherHeroSection',
  data() {
    return {
      title: 'Forecast Gods',
      titleToChange: 'Forecast Gods',
      infoResponse: 'Current temperature (in Celsius) is: ',
      currentW: 32,
      buttonContentIncrease: 'Click me to increase value.',
      buttonContentDecrease: 'Click me to decrease value',
      userName: "mike",
      showSubBottom: false,
    }
  },
  methods: {
    changeTitle() {
      //We have to use THIS keyword in order to change data from data component.
      this.titleToChange = `Title changed by method!`;
      this.showSubBottom = !this.showSubBottom;
    }
  }
};

</script>

<style lang="scss" src="./WeatherHeroSection.scss" />
