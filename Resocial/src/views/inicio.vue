<template>
<div class="Baner">
    <p><code>wrapAround: true</code></p>

<!-- Flickity HTML init -->
<div class="gallery js-flickity"
  data-flickity-options='{ "wrapAround": true }'>
  <div class="gallery-cell">
    <img src="/img/Baner.jpg" alt="">
  </div>
  <div class="gallery-cell">
    <img src="/img/Baner.jpg" alt="">
  </div>
  <div class="gallery-cell">
    <img src="/img/Baner.jpg" alt="">
  </div>
  <div class="gallery-cell">
    <img src="/img/Baner.jpg" alt="">
  </div>
  <div class="gallery-cell">
    <img src="/img/Baner.jpg" alt="">
  </div>
</div>
</div>
</template>
<style>
/* Baner */
/* external css: flickity.css */
* {
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}

body { font-family: sans-serif; }

.gallery {
  background: #EEE;
}

.gallery-cell {
  width: 66%;
  height: 200px;
  margin-right: 10px;
  background: #8C8;
  counter-increment: gallery-cell;
}

/* cell number */
.gallery-cell:before {
  display: block;
  text-align: center;
  content: counter(gallery-cell);
  line-height: 200px;
  font-size: 80px;
  color: white;
}
</style>
<script>
</script>
