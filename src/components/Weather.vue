<template>
  <div class="weather-container">
    <p class="city">{{ city }}</p>
    <p class="temp">{{ temperature }}°C</p>
    <img :src="iconUrl" alt="weather condition icon" class="condition-icon" />
    <p class="condition">{{ weather }}</p>
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
  position: relative;
  background: rgb(127, 186, 231);
  background: linear-gradient(
    120deg,
    rgba(127, 186, 231, 1) 6%,
    rgba(84, 179, 195, 1) 94%
  );
  width: 300px;
  height: 300px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 1rem;
  padding: 1rem;
  border: 0;
  border-radius: 10px;
  box-shadow: 8px 8px 13px #e6e6e6, -8px -8px 13px #ffffff;
  margin: auto;
  color: #e6e6e6;
}

.city {
  font-size: 2.5rem;
}
.temp {
  font-size: 3.5rem;
}
.condition {
  font-size: 1.5rem;
}
</style>
