<script setup></script>

<template>
  <div class="cal">
    <div class="cal-heading">
      <h1>Calendar</h1>
    </div>
    <div class="cal-date">
      <h2>12</h2>
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
.cal {
  position: relative;
  width: 300px;
  height: 300px;
  display: grid;
  text-align: left;
  padding: 1rem;
  border: 0px solid black;
  border-radius: 10px;

  box-shadow: 8px 8px 13px #e6e6e6, -8px -8px 13px #ffffff;
  margin: auto;

  grid-template-areas:
    "box1 box2"
    "box3 box3"
    "box3 box3";

  grid-template-rows: 1fr 3fr;
  grid-template-columns: 1fr 2fr;
}

.cal-heading {
  grid-area: box1;
  font-size: 1rem;
  color: red;
}

.cal-date {
  font-size: 7rem;
  color: red;
  opacity: 0.2;
  display: flex;
  align-items: center;
  justify-content: center;
  position: absolute;
  right: 1rem;
  bottom: 1rem;
  z-index: -1;
}

.entries {
  grid-area: box3;
}

.time {
  font-size: 1rem;
  color: gray;
}

.definition {
  font-size: 1.55rem;
}
</style>
