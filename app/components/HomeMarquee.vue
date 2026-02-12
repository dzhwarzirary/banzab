<template>
  <section class="section-sheet sheet-2">
    <div class="sheet-content overflow-hidden">
      <div class="py-14 md:py-20">
        <!-- Marquee Track -->
        <div class="marquee-container">
          <div class="marquee-track">
            <span
              v-for="n in 2"
              :key="n"
              class="marquee-content"
              aria-hidden="n > 1"
            >
              <span class="marquee-item">Smoothie Season</span>
              <span class="marquee-dot"></span>
              <span class="marquee-item">Pyarra</span>
              <span class="marquee-dot"></span>
              <span class="marquee-item text-gray-300">Quality First</span>
              <span class="marquee-dot"></span>
              <span class="marquee-item">Smoothie Season</span>
              <span class="marquee-dot"></span>
              <span class="marquee-item">Pyarra</span>
              <span class="marquee-dot"></span>
              <span class="marquee-item text-gray-300">Built in Kurdistan</span>
              <span class="marquee-dot"></span>
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.marquee-container {
  width: 100%;
  overflow: hidden;
  -webkit-mask-image: linear-gradient(
    to right,
    transparent,
    black 10%,
    black 90%,
    transparent
  );
  mask-image: linear-gradient(
    to right,
    transparent,
    black 10%,
    black 90%,
    transparent
  );
}

.marquee-track {
  display: flex;
  width: max-content;
  animation: marquee 30s linear infinite;
}

.marquee-content {
  display: flex;
  align-items: center;
  gap: 0;
  flex-shrink: 0;
}

.marquee-item {
  font-size: clamp(2rem, 5vw, 4rem);
  font-weight: 300;
  color: #111827;
  letter-spacing: -0.025em;
  white-space: nowrap;
  padding: 0 1.5rem;
}

.marquee-dot {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: #d1d5db;
  flex-shrink: 0;
}

@keyframes marquee {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-50%);
  }
}

@media (max-width: 768px) {
  .marquee-item {
    padding: 0 1rem;
  }

  .marquee-dot {
    width: 6px;
    height: 6px;
  }
}
</style>
