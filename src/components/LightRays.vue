<template>
  <div class="light-rays"></div>
</template>

<style scoped>
.light-rays {
  position: absolute;
  inset: 0;
  background: linear-gradient(
    115deg,
    transparent 35%,
    rgba(255, 231, 165, 0.15) 45%,
    transparent 55%
  );
  animation: rayMove 8s ease-in-out infinite alternate;
  pointer-events: none;
}

@keyframes rayMove {
  from {
    opacity: 0.3;
  }
  to {
    opacity: 0.8;
  }
}
</style>
