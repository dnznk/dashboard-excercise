<script setup>
import Header from "./components/Header.vue";
import Calendar from "./components/Calendar.vue";
import Weather from "./components/Weather.vue";
import Unsplash from "./components/Unsplash.vue";
import News from "./components/News.vue";
import Maps from "./components/Maps.vue";
import Animation from "./components/Animation.vue";
</script>

<template>
  <Header />
  <Calendar />
  <Maps />
  <Weather />
  <News />
  <Unsplash />
  <Animation />
</template>

<style scoped>
.box {
  position: relative;
  width: 300px;
  height: 300px;
  border-radius: 10px;
  box-shadow: 4.5px 4.5px 25px #dddedb, -4.5px -4.5px 25px #ffffff;
}
</style>
