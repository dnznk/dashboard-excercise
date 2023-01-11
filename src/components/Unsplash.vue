<template>
  <div class="unsplash-container">
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
.unsplash-container {
  position: relative;
  width: 300px;
  height: 300px;
  border: 0;
  border-radius: 10px;
  box-shadow: 8px 8px 13px #e6e6e6, -8px -8px 13px #ffffff;
  margin: auto;
}

.unsplash-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border: 0;
  border-radius: 10px;
}
</style>
