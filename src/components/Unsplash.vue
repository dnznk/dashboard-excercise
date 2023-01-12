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
  position: absolute;
  bottom: 15px;
  left: 0;
  width: fit-content;
  height: fit-content;
  font-size: 1.05rem;
  color: hotpink;
  /* background: linear-gradient(
    hsl(0 0% 0% / 0),
    hsl(20 0% 0% / 0.3) 20%,
    hsl(0 0% 0% / 1)
  ); */
  writing-mode: vertical-rl;
  text-orientation: mixed;
}
</style>
