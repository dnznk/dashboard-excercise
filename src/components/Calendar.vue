<script setup></script>

<template>
  <div class="cal">
    <div class="cal-heading">
      <h1>Calendar</h1>
    </div>
    <div class="cal-date">
      <h2>12</h2>
    </div>
    <div class="first entry">
      <p class="time">12:00</p>
      <p class="definition">Zoom Meeting</p>
    </div>
    <div class="second entry">
      <p class="time">14:00</p>
      <p class="definition">Lunch</p>
    </div>
  </div>
</template>

<style>
.cal {
  width: 300px;
  height: 300px;
  display: grid;
  text-align: left;
  padding: 1rem;
  border: 1px solid black;
  border-radius: 8px;
  margin: auto;
}
</style>
