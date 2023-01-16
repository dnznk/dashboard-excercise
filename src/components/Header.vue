<template>
  <div class="header-container">
    <div class="profile-img"><img src="../assets/profile.png" alt="" /></div>
    <div class="time-greeting box">
      <div class="greeting">{{ greeting }}</div>
      <div class="current-time">BERLIN ◉ {{ berlinTime }}</div>
    </div>
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
    // Testing
    // let currentHour = 0;
    if (currentHour >= 22 || currentHour < 6) {
      this.greeting = "Good night!";
    } else if (currentHour >= 6 && currentHour < 12) {
      this.greeting = "Good morning!";
    } else if (currentHour >= 12 && currentHour < 18) {
      this.greeting = "Good afternoon!";
    } else if (currentHour >= 18 && currentHour < 22) {
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
.header-container {
  width: fit-content;
  display: flex;
  justify-content: flex-start;
  place-items: center;
  gap: 2rem;
  padding-bottom: 2rem;
}

.profile-img img {
  width: clamp(64px, 5vmax, 128px);
  height: clamp(64px, 5vmax, 128px);
  border-radius: 50%;
}

.greeting {
  font-size: clamp(2rem, 5vmin, 3rem);
  font-family: "Space Mono", monospace;
  color: black;
}

.current-time {
  font-size: 0.9rem;
  font-family: monospace;
  color: white;
  background-color: black;
  border-radius: 30px 100px;
  padding: 0.5rem 1rem;
}
</style>
