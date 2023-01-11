<script setup>
import Header from "./components/Header.vue";
import Calendar from "./components/Calendar.vue";
import Weather from "./components/Weather.vue";
</script>

<template>
  <header>
    <Header />
  </header>

  <main>
    <Calendar />
    <Weather />
  </main>
</template>

<style scoped></style>
