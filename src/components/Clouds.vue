<template>
  <div class="cloud clound-one"></div>
  <div class="cloud clound-two"></div>
</template>

<style scoped>
.cloud {
  position: absolute;
  width: 160px;
  height: 45px;
  border-radius: 50px;
  background: rgba(255, 255, 255, 0.16);
  filter: blur(10px);
}

.cloud-one {
  top: 22%;
  left: -220px;
  animation: cloudMove 35s linear infinite;
}

.cloud-two {
  top: 35%;
  left: -220px;
  opacity: -6;
  animation: cloudMove 48s linear infinite 5s;
}

@keyframes cloudMove {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(130vw);
  }
}
</style>
