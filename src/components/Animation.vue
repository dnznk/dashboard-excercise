<template>
  <div class="animation-container box">
    <button id="play-pause-button" @click="toggleAnimation">
      ENGINE ON/OFF
    </button>
    <img id="rocket" src="../assets/rocket.png" alt="" />
  </div>
</template>
<script>
export default {
  methods: {
    toggleAnimation() {
      let rocket = document.getElementById("rocket");
      if (rocket.style.animationPlayState === "running") {
        rocket.style.animationPlayState = "paused";
      } else {
        rocket.style.animationPlayState = "running";
      }
    },
  },
};
</script>
<style>
.animation-container {
  background-image: radial-gradient(yellow 2%, transparent 2%),
    radial-gradient(yellow 3%, transparent 5%);
  background-color: black;
  background-position: 0 0, 50px 50px;
  background-size: 100px 100px;
}

.button {
  position: absolute;
  top: 50%;
  left: 50%;
}
.button button {
  width: fit-content;
  background-color: rgb(255, 105, 180);
  color: black;
  padding: 0.75rem 1rem;
}

#play-pause-button {
  position: absolute;
  width: fit-content;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background: rgba(255, 105, 180, 0.9);
  border: 0;
  border-radius: 10px;
  padding: 0.5rem 1rem;
  color: purple;
  font-size: 1rem;
  mix-blend-mode: screen;
  color: black;
  font-family: "Space Mono", monospace;
}

#rocket {
  position: absolute;
  bottom: 0px;
  left: 0px;
  animation: moveRocket 8s linear 500ms infinite;
  transform: rotate(90deg);
  animation-play-state: paused;
}

@keyframes moveRocket {
  0% {
    bottom: 5px;
    left: 5px;
    transform: rotate(90deg);
  }
  25% {
    bottom: 5px;
    left: 231px;
    transform: rotate(0deg);
  }
  50% {
    bottom: 231px;
    left: 231px;
    transform: rotate(-90deg);
  }
  75% {
    bottom: 231px;
    left: 5px;
    transform: rotate(-180deg);
  }
  100% {
    bottom: 5px;
    left: 5px;
    transform: rotate(-270deg);
  }
}
</style>
