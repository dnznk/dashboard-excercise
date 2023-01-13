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
  <div class="grid-container">
    <Calendar />
    <Maps />
    <Weather />
    <News />
    <Unsplash />
    <Animation />
  </div>
</template>

<style scoped>
.grid-container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  grid-auto-flow: row;
  gap: 2rem;
}

.box {
  position: relative;
  width: 300px;
  height: 300px;
  border-radius: 10px;
  box-shadow: 4.5px 4.5px 25px #dddedb, -4.5px -4.5px 25px #ffffff;
}
</style>
