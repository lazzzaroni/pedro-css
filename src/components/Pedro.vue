<template>
  <div
    class="w-auto max-w-72 sm:max-w-96 h-auto overflow-hidden rounded-full mx-auto"
    :class="spin"
  >
    <img
      class="scale-110"
      :class="bounce"
      src="/pedro.webp"
      alt="Pedro The Raccoon"
    />
  </div>

  <div class="w-32">
    <button
      v-if="!isPlayed"
      class="w-full rounded-md bg-indigo-600 px-3 py-2 text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600"
      @click="launch"
    >
      play
    </button>
    <button
      v-else
      class="w-full rounded-md bg-indigo-600 px-3 py-2 text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600"
      @click="stop"
    >
      stop
    </button>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

const spin = ref("");
const bounce = ref("");
const isPlayed = ref(false);
const timeoutId = ref(0);
const audio = ref(new Audio("/src/assets/pedro.mp3"));

function startBounce() {
  timeoutId.value = setTimeout(() => (bounce.value = "bounce"), 7500);
}

function stopBounce() {
  clearTimeout(timeoutId.value);
}

audio.value.onended = () => {
  stop();
};

function launch() {
  spin.value = "spin";
  startBounce();
  isPlayed.value = true;
  audio.value.play().catch((error) => {
    console.error("Error playing audio:", error);
  });
}

function stop() {
  spin.value = "";
  bounce.value = "";
  stopBounce();
  isPlayed.value = false;
  audio.value.load();
}
</script>

<style scoped>
@keyframes bounce {
  to {
    translate: 0 0.75rem;
  }
}
.bounce {
  animation: bounce 200ms linear infinite alternate;
}

@keyframes spin {
  to {
    rotate: -1turn;
  }
}
.spin {
  animation: spin 10s linear infinite;
}
</style>
