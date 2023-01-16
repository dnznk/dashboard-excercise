<template>
  <div class="unsplash-container box">
    <img :src="imageUrl" alt="random unsplash image" class="unsplash-img" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      imageUrl: "",
    };
  },
  created() {
    const url =
      "https://api.unsplash.com/photos/random?client_id=byblphPvtiYsqblwl8BLg5o6LN-auzOP-N700QqohE0";
    fetch(url)
      .then((res) => res.json())
      .then((data) => {
        this.imageUrl = data.urls.regular;
      });
  },
};
</script>

<style>
.unsplash-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border: 0;
  border-radius: 10px;
}

.unsplash-container::after {
  content: "Random Unsplash";
  font-size: 0.8rem;
  font-weight: bold;
  color: hotpink;
  position: absolute;
  bottom: 10px;
  left: 2px;
  width: fit-content;
  height: fit-content;
  writing-mode: vertical-rl;
  text-orientation: mixed;
}
</style>
