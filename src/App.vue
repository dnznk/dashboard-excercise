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
  /* Template I used before for easier setup*/
  /*User input values.*/
  --grid-layout-gap: 2rem;
  --grid-column-count: 3;
  --grid-item--min-width: 300px;

  /*Calculated values.*/
  --gap-count: calc(var(--grid-column-count) - 1);
  --total-gap-width: calc(var(--gap-count) * var(--grid-layout-gap));
  --grid-item--max-width: calc(
    (100% - var(--total-gap-width)) / var(--grid-column-count)
  );

  display: grid;
  grid-template-columns: repeat(
    auto-fit,
    minmax(max(var(--grid-item--min-width), var(--grid-item--max-width)), 1fr)
  );
  grid-gap: var(--grid-layout-gap);
  justify-items: center;
}

.box {
  position: relative;
  width: 300px;
  height: 300px;
  border-radius: 15px;
  box-shadow: 5px 5px 10px #aeaeae;
}
</style>
