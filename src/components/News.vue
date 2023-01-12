<template>
  <div class="news-container box">
    <div class="news-content">
      <h2 class="news-title">Latest tech news</h2>
      <p class="news-body">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Fugiat rem
        facilis.
      </p>
      <a href="#" class="news-button">Learn More</a>
    </div>
  </div>
</template>

<style>
.news-container {
  background-color: white;
  text-align: left;
  background-image: url(https://images.unsplash.com/photo-1550745165-9bc0b252726f?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2340&q=80);
  background-size: cover;
  color: #e6e6e6;
}

.news-content {
  position: absolute;
  bottom: 0;
  border-radius: inherit;
  --padding: 1.5rem;
  padding: var(--padding);
  background: linear-gradient(
    hsl(0 0% 0% / 0),
    hsl(20 0% 0% / 0.3) 20%,
    hsl(0 0% 0% / 1)
  );
}

.news-body {
  padding: 1rem 0;
}

.news-title {
  width: max-content;
}

.news-title::after {
  content: "";
  position: absolute;
  height: 4px;
  width: calc(100% + var(--padding));
  left: calc(var(--padding) * -1);
  bottom: -2px;
  background: hotpink;
  transform-origin: left;
  transition: transform 500ms ease;
}

.news-button {
  cursor: pointer;
  display: inline-block;
  text-decoration: none;
  color: black;
  background: hotpink;
  padding: 0.5em 1.25em;
  border-radius: 0.25rem;
}

.news-button:hover,
.news-button:focus {
  background-color: greenyellow;
}
</style>
