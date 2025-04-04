<template>
  <div class="fixed top-0 left-0 z-50 pointer-events-none">
    <canvas id="fluid" class="w-screen h-screen"></canvas>
  </div>
</template>

<script setup>
import { onMounted, onUnmounted } from 'vue';
import useFluidCursor from '../composables/useFluidCursor';

onMounted(() => {
  useFluidCursor();
});
</script>
