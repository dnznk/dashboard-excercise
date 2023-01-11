<script setup>
let url =
  "http://api.weatherapi.com/v1/current.json?key=2488d77e17e841dc887135638231101&q=Berlin&aqi=no";

fetch(url)
  .then((res) => res.json())
  .then((data) => {
    console.log(data);
  });
</script>

<template>
  <div class="weather">
    <p class="city">Berlin</p>
    <p class="temp">6 C</p>
    <p class="condition">Cloudy</p>
  </div>
</template>

<style>
.weather {
  position: relative;
  background: rgb(127, 231, 212);
  background: linear-gradient(
    18deg,
    rgba(127, 231, 212, 1) 35%,
    rgba(0, 212, 255, 1) 100%
  );
  width: 300px;
  height: 300px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 1rem;
  padding: 1rem;
  border: 0px solid black;
  border-radius: 10px;

  box-shadow: 8px 8px 13px #e6e6e6, -8px -8px 13px #ffffff;
  margin: auto;
}

.city {
  font-size: 1.5rem;
}
.temp {
  font-size: 3rem;
}
.condition {
  font-size: 1rem;
}
</style>
