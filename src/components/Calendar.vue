<script setup>
let a = new Date();
let day = a.getDate();
</script>

<template>
  <div class="calendar-container box">
    <div class="cal-heading">
      <h1>Calendar</h1>
    </div>
    <div class="cal-date">
      <h2>{{ day }}</h2>
    </div>
    <div class="entries">
      <div class="first entry">
        <p class="time">12:00</p>
        <p class="definition">Zoom Meeting</p>
      </div>
      <div class="second entry">
        <p class="time">14:00</p>
        <p class="definition">Lunch</p>
      </div>
    </div>
  </div>
</template>

<style>
.calendar-container {
  background-color: white;
  text-align: left;
  padding: 1rem;
}

.cal-heading {
  font-size: 1rem;
  color: red;
  padding-bottom: 1rem;
}

.cal-date {
  font-size: 9rem;
  color: red;
  opacity: 0.2;
  display: flex;
  align-items: center;
  justify-content: center;
  position: absolute;
  right: 1rem;
  bottom: 1rem;
}

.time {
  font-size: 1rem;
  color: gray;
}

.definition {
  font-size: 1.55rem;
}
</style>
