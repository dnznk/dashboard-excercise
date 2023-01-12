<template>
  <div id="map" class="box"></div>
</template>

<script>
export default {
  name: "OpenStreetMap",
  data() {
    return {
      address: "Space Squad 🚀",
    };
  },
  mounted() {
    this.initMap();
  },
  methods: {
    initMap() {
      var map = L.map("map").setView([52.4683, 13.38981], 15);
      L.tileLayer("https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png", {
        attribution:
          '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors',
      }).addTo(map);
      var marker = L.marker([52.4683, 13.38981]).addTo(map);
      marker.bindPopup(this.address).openPopup();
    },
  },
};
</script>

<style>
#map {
  width: 300px;
  height: 300px;
  border-radius: 10px;
  z-index: 0;
}
</style>
