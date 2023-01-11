<script setup>
import Header from "./components/Header.vue";
import Calendar from "./components/Calendar.vue";
import Weather from "./components/Weather.vue";
import Unsplash from "./components/Unsplash.vue";
</script>

<template>
  <header>
    <Header />
  </header>

  <main>
    <Calendar />
    <Weather />
    <Unsplash />
  </main>
</template>

<style scoped></style>
