<template>
  <div class="butterfly butterfly-one">🦋</div>
  <div class="butterfly butterfly-two">🦋</div>
</template>

<style scoped>
.butterfly {
  position: absolute;
  font-size: 28px;
  z-index: 2;
}

.butterfly-one {
  top: 48%;
  left: 20%;
  animation: butterflyFly 9s ease-in-out infinite;
}

.butterfly-two {
  top: 60%;
  left: 70%;
  animation: butterflyFly 12s ease-in-out infinite reverse;
}

@keyframes butterflyFly {
  0%,
  100% {
    transform: translate(0, 0) rotate(0);
  }
  25% {
    transform: translate(50px, -40px) rotate(15deg);
  }
  50% {
    transform: translate(100px, 10px) rotate(-10deg);
  }
  75% {
    transform: translate(40px, 60px) rotate(10deg);
  }
}
</style>
