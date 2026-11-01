<script setup>
import { ref } from "vue";
import NatureScene from "./components/NatureScene.vue";
import NatureInfo from "./components/NatureInfo.vue";

const playing = ref(true);
const offsetX = ref(0);

function toggleAnimation() {
  playing.value = !playing.value;
}

function handleMouseMove(event) {
  offsetX.value = (event.clientX / window.innerWidth - 0.5) * 40;
}
</script>

<template>
  <main @mousemove="handleMouseMove">
    <nav class="navbar">
      <div class="logo">NATURE<span>.</span></div>

      <div class="nav-links">
        <a href="#home">Home</a>
        <a href="#about">About</a>
        <a href="#explore">Explore</a>
      </div>

      <div class="nav-status"><span></span> LIVE EXPERIENCE</div>
    </nav>

    <section class="hero" id="home">
      <NatureInfo :playing="playing" @toggle="toggleAnimation" />

      <div class="scene-container" id="explore">
        <NatureScene :playing="playing" :offset-x="offsetX" />
      </div>
    </section>

    <footer>
      <span>© 2026 NATURE MOTION</span>
      <span>DESIGNED WITH VUE.JS</span>
    </footer>
  </main>
</template>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: #101c18;
}

main {
  min-height: 100vh;
  color: white;
  overflow: hidden;
}

.navbar {
  height: 85px;
  padding: 0 7%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.logo {
  font-size: 25px;
  font-weight: 900;
}

.logo span {
  color: #a5d9ad;
}

.nav-links {
  display: flex;
  gap: 35px;
}

.nav-links a {
  color: #bdc9c1;
  text-decoration: none;
  font-size: 14px;
  transition: 0.3s;
}

.nav-links a:hover {
  color: #a5d9ad;
}

.nav-status {
  font-size: 10px;
  letter-spacing: 2px;
  color: #a5d9ad;
}

.nav-status span {
  display: inline-block;
  width: 7px;
  height: 7px;
  border-radius: 50%;
  background: #a5d9ad;
  margin-right: 8px;
}

.hero {
  min-height: calc(100vh - 140px);
  display: grid;
  grid-template-columns: 1fr 1fr;
  align-items: center;
  padding: 40px 7%;
  gap: 35px;
}

.scene-container {
  width: 100%;
  border-radius: 25px;
  overflow: hidden;
  box-shadow: 0 25px 80px rgba(0, 0, 0, 0.4);
}

footer {
  padding: 25px 7%;
  display: flex;
  justify-content: space-between;
  font-size: 10px;
  letter-spacing: 2px;
  color: #82958a;
}

@media (max-width: 800px) {
  .hero {
    grid-template-columns: 1fr;
    padding: 30px 5%;
  }

  .nav-links {
    display: none;
  }

  .nav-status {
    font-size: 8px;
  }
}

@media (max-width: 480px) {
  footer {
    gap: 15px;
    font-size: 8px;
  }
}
</style>
