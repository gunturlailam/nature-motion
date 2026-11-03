<template>
  <div class="sun"></div>
</template>

<style scoped>
.sun {
  position: absolute;
  width: 115px;
  height: 115px;
  top: 15%;
  right: 23%;
  border-radius: 50%;
  background: #ffe9a6;
  box-shadow:
    0 0 40px #ffe9a6,
    0 0 100px rgba(255, 220, 130, 6);
  animation: sunGlow 4s ease-in-out infinite alternate;
}

@keyframes sunGlow {
  from {
    transform: scale(1);
  }
  to {
    transform: scale(1.12);
  }
}

@media (max-width: 600px) {
  .sun {
    width: 75px;
    height: 75px;
  }
}
</style>
