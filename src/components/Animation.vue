<template>
  <div class="animation-container box">
    <img id="rocket" src="../assets/rocket.png" alt="" />
  </div>
</template>
<script>
// export default {
//   data() {
//     return {
//       isActive: false,
//     };
//   },
// };
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
  background-color: hotpink;
  color: black;
  padding: 0.75rem 1rem;
}

#rocket {
  position: absolute;
  bottom: 0px;
  left: 0px;
  animation: moveRocket 8s linear 500ms infinite;
  transform: rotate(90deg);
  animation-play-state: running;
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
