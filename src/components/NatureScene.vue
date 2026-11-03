<script setup>
import Sun from "./Sun.vue";
import Clouds from "./Clouds.vue";
import LightRays from "./LightRays.vue";
import Wildlife from "./Wildlife.vue";

defineProps({
  playing: Boolean,
  offsetX: Number,
});
</script>

<template>
  <section class="nature-scene" :class="{ paused: !playing }">
    <div
      class="forest"
      :style="{
        transform: `scale(1.08) translateX(${-offsetX * 0.15}px)`,
      }"
    ></div>

    <Sun />
    <Clouds />
    <LightRays />
    <Wildlife />

    <div class="foreground"></div>

    <div class="scene-label">
      <span class="live-dot"></span>
      NATURE IS ALIVE
    </div>
  </section>
</template>

<style scoped>
.nature-scene {
  position: relative;
  width: 100%;
  min-height: 480px;
  height: 100%;
  overflow: hidden;
  background: linear-gradient(180deg, #162f38, #527a70 55%, #142d25);
  isolation: isolate;
}

.forest {
  position: absolute;
  inset: 0;
  z-index: -1;
  background:
    linear-gradient(180deg, rgba(5, 20, 19, 0.05), rgba(5, 20, 19, 0.25)),
    url("https://images.unsplash.com/photo-1448375240586-882707db888b?w=1800")
      center / cover no-repeat;
  transition: transform 0.3s ease-out;
}

.foreground {
  position: absolute;
  bottom: 0;
  width: 100%;
  height: 22%;
  background: linear-gradient(0deg, #10271d, rgba(16, 39, 85) 55%, transparent);
  pointer-events: none;
}

.scene-label {
  position: absolute;
  bottom: 25px;
  left: 30px;
  color: white;
  font-size: 11px;
  letter-spacing: 3px;
  font-weight: bold;
}

.live-dot {
  display: inline-block;
  width: 8px;
  height: 8px;
  background: #8ddfad;
  border-radius: 50%;
  margin-right: 8px;
  box-shadow: 0 0 10px #8dffad;
}

.paused :deep(*) {
  animation-play-state: paused !important;
}

@media (max-width: 600px) {
  .nature-scene {
    min-height: 380px;
  }
}
</style>
