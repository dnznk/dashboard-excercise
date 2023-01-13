<template>
  <div class="weather-container box">
    <p class="city">{{ city }}</p>
    <p class="temp">{{ temperature }}°C</p>
    <div class="weather">
      <img :src="iconUrl" alt="weather condition icon" class="condition-icon" />

      <p class="condition">{{ weather }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      city: "",
      temperature: "",
      weather: "",
      iconUrl: "",
    };
  },
  created() {
    const url =
      "http://api.weatherapi.com/v1/current.json?key=2488d77e17e841dc887135638231101&q=Berlin&aqi=no";
    fetch(url)
      .then((res) => res.json())
      .then((data) => {
        this.city = data.location.name;
        this.temperature = data.current.temp_c;
        this.weather = data.current.condition.text;
        this.iconUrl = data.current.condition.icon;
      });
  },
};
</script>

<style>
.weather-container {
  background: rgb(127, 186, 231);
  background: linear-gradient(
    120deg,
    rgba(127, 186, 231, 1) 6%,
    rgba(84, 179, 195, 1) 94%
  );
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 0.1rem;
  padding: 1rem;
  color: #e6e6e6;
  font-family: "Inter", sans-serif;
}

.city {
  font-size: 2.5rem;
}
.temp {
  font-size: 3.5rem;
}
.condition {
  font-size: 1.25rem;
}
.weather {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
