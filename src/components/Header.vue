<template>
  <div class="greeting-container">
    <div class="profile-img"><img src="../assets/profile.png" alt="" /></div>
    <div class="greeting">{{ greeting }}</div>
    <div class="current-time">BERLIN - {{ berlinTime }}</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      greeting: "",
      berlinTime: new Date().toLocaleString("de-DE", {
        timeZone: "Europe/Berlin",
      }),
    };
  },
  created() {
    let currentHour = new Date().getHours();
    if (currentHour < 12) {
      this.greeting = "Good morning!";
    } else if (currentHour < 18) {
      this.greeting = "Good afternoon!";
    } else {
      this.greeting = "Good evening!";
    }
  },
  methods: {
    updateTime: function () {
      this.berlinTime = new Date().toLocaleString("de-DE", {
        timeZone: "Europe/Berlin",
      });
    },
  },
  mounted() {
    setInterval(this.updateTime, 1000);
  },
};
</script>

<style>
.greeting-container {
  display: flex;
  justify-content: space-between;
  place-items: center;
  padding: 1rem;
}

.profile-img img {
  width: 10vmin;
  height: 10vmin;
  border-radius: 50%;
}

.greeting {
  font-size: clamp(2rem, 5vmin, 3rem);
  color: black;
  align-self: flex-end;
}

.current-time {
  position: absolute;
  top: 1rem;
  right: 1rem;
  font-size: clamp(0.25rem, 1vmin, 0.75rem);
  font-family: monospace;
  background-color: black;
  color: white;
  padding: 0.75rem;
}
</style>
