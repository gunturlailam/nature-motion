<script setup>
defineProps({
  playing: Boolean,
});

defineEmits(["toggle"]);
</script>

<template>
  <section class="nature-info" id="about">
    <div class="tag">✦ EXPLORE THE WILD</div>

    <h1>
      Discover the
      <span>Beauty of Nature.</span>
    </h1>

    <p>
      Nature is not a place to visit. It is home. Take a moment, breathe, and
      reconnect with the beauty of the earth.
    </p>

    <button @click="$emit('toggle')">
      {{ playing ? "❚❚ Pause Animation" : "▶ Play Animation" }}
    </button>

    <div class="stats">
      <div>
        <strong>01</strong>
        <span>Forest</span>
      </div>

      <div>
        <strong>02</strong>
        <span>Wildlife</span>
      </div>

      <div>
        <strong>03</strong>
        <span>Peace</span>
      </div>
    </div>
  </section>
</template>

<style scoped>
.nature-info {
  max-width: 650px;
  padding: 50px 30px;
  color: white;
}

.tag {
  color: #a5d9ad;
  font-size: 12px;
  letter-spacing: 3px;
  margin-bottom: 22px;
}

h1 {
  font-size: clamp(36px, 6vw, 70px);
  line-height: 1.05;
  margin: 0;
  font-weight: 800;
}

h1 span {
  display: block;
  color: #a5d9ad;
}

p {
  color: #c1d0c6;
  font-size: 16px;
  line-height: 1.8;
  max-width: 470px;
  margin: 25px 0;
}

button {
  background: #a5d9ad;
  color: #12271c;
  border: none;
  padding: 15px 25px;
  border-radius: 30px;
  font-weight: bold;
  cursor: pointer;
  transition: 0.3s;
}

button:hover {
  transform: translateY(-4px);
  background: white;
}

.stats {
  display: flex;
  gap: 20px;
  margin-top: 50px;
}

.stats div {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.stats strong {
  font-size: 25px;
  color: #a5d9ad;
}

.stats span {
  font-size: 12px;
  color: #aebeb3;
  letter-spacing: 1px;
}
</style>
