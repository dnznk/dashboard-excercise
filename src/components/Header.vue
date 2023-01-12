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
  width: 100%;
}

.profile-img img {
  width: 5vmin;
  height: 5vmin;
  border-radius: 50%;
}

.greeting {
  font-size: clamp(1rem, 2vmin, 5rem);
  color: black;
  align-self: flex-end;
}
</style>
