<template>
  <div class="header-container">
    <div class="profile-img"><img src="../assets/profile.png" alt="" /></div>
    <div class="time-greeting box">
      <div class="greeting">{{ greeting }}</div>
      <div class="current-time">BERLIN - {{ berlinTime }}</div>
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
.header-container {
  display: flex;
  justify-content: flex-start;
  place-items: center;
  gap: 2rem;
  padding-bottom: 2rem;
  width: fit-content;
}

.profile-img img {
  width: clamp(64px, 5vmax, 128px);
  height: clamp(64px, 5vmax, 128px);
  border-radius: 50%;
}

.greeting {
  font-size: clamp(2rem, 5vmin, 3rem);
  color: black;
  font-family: "Space Mono", monospace;
}

.current-time {
  font-size: 0.9rem;
  font-family: monospace;
  background-color: black;
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 30px 100px;
  /* border-radius: 0 100px 100px 0; */
}
</style>
