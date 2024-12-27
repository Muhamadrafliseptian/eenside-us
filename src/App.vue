<script setup>
import { ref } from 'vue';
import NavbarLayout from './components/layouts/navbar/NavbarComponents.vue'

const videoRef = ref(null);

const playVideo = () => {
  videoRef.value.play();
};
</script>

<template>
  <!-- <NavbarLayout/> -->
  <RouterView/>
</template>

<style scoped>
/* Container styling to manage responsiveness */
.video-container {
  position: relative;
  width: 100%;
  max-width: 600px;
  /* Set a maximum width for larger screens */
  margin: 0 auto;
  /* Center the video */
  overflow: hidden;
  border-radius: 12px;
  /* Rounded corners */
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
  /* Optional shadow for better aesthetics */
}

/* Responsive video */
.responsive-video {
  width: 100%;
  /* Video adjusts to container width */
  height: auto;
  /* Maintain aspect ratio */
  display: block;
  /* Remove unwanted whitespace below the video */
}

/* Play button overlay */
.play-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  background: rgba(0, 0, 0, 0.5);
  /* Semi-transparent overlay */
  color: white;
  opacity: 0;
  transition: opacity 0.3s;
}

.play-overlay:hover {
  opacity: 1;
  /* Show overlay on hover */
}

.play-button {
  background: none;
  border: none;
  font-size: 2rem;
  color: white;
  cursor: pointer;
  padding: 0.5rem 1rem;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.2);
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
  transition: background 0.3s;
}

.play-button:hover {
  background: rgba(255, 255, 255, 0.4);
}
</style>
