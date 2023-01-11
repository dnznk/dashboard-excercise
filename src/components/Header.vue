<script setup></script>

<template>
  <div class="greeting-container">
    <div class="profile-img"><img src="../assets/profile.png" alt="" /></div>
    <div class="greeting">Good morning!</div>
  </div>
</template>

<style>
.greeting-container {
  width: 100vw;
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
