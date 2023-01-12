<script>
export default {
  data() {
    return {
      greeting: "",
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
};
</script>

<template>
  <div class="greeting-container">
    <div class="profile-img"><img src="../assets/profile.png" alt="" /></div>
    <div class="greeting">{{ greeting }}</div>
  </div>
</template>

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
  font-size: clamp(1rem, 5vmin, 5rem);
  color: black;
}
</style>
