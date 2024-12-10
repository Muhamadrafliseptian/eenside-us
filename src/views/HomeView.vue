<script setup>
import TheWelcome from '../components/TheWelcome.vue'
import sound from '../assets/video/katakan.mp3'
import { ref, onMounted } from 'vue';

const audio = new Audio(sound);

// Function untuk memutar lagu
const playMusic = () => {
  audio.play();
};

const countdown = ref({
  days: 0,
  hours: 0,
  minutes: 0,
  seconds: 0,
});

const targetDate = new Date('2024-12-28T00:00:00+07:00'); // Waktu dalam zona WIB

// Function untuk memperbarui countdown
const updateCountdown = () => {
  const now = new Date();
  const difference = targetDate - now;

  if (difference > 0) {
    countdown.value = {
      days: Math.floor(difference / (1000 * 60 * 60 * 24)),
      hours: Math.floor((difference / (1000 * 60 * 60)) % 24),
      minutes: Math.floor((difference / (1000 * 60)) % 60),
      seconds: Math.floor((difference / 1000) % 60),
    };
  } else {
    countdown.value = {
      days: 0,
      hours: 0,
      minutes: 0,
      seconds: 0,
    };
  }
};

// Jalankan updateCountdown secara berkala
onMounted(() => {
  updateCountdown(); // Panggilan awal
  setInterval(updateCountdown, 1000); // Perbarui setiap detik
});
</script>

<template>
  <div class="container my-5">
    <div class="row p-4 pb-0 pe-lg-0 pt-lg-5 align-items-center">
      <div class="col-lg-7 p-3 p-lg-5 pt-lg-3">
        <h1 class="display-4 fw-bold lh-1 text-body-emphasis">
          Otw Jadi Bucket
        </h1>
        <p class="lead">
          {{ countdown.days }} Hari
          {{ countdown.hours }} Jam
          {{ countdown.minutes }} Menit
          {{ countdown.seconds }} Detik
        </p>
        <div class="d-grid gap-2 d-md-flex justify-content-md-start mb-4 mb-lg-3">
          <button type="button" class="btn btn-primary btn-lg px-4 me-md-2 fw-bold"
          @click="playMusic"
          >
            <p class="text-light mt-0 mb-0">
              Pake Lagu Biar Asik
            </p>
          </button>
          <button type="button" class="btn btn-outline-secondary btn-lg px-4">Lanjut Scroll dulu deh</button>
        </div>
      </div>
      <div class="col-lg-4">
        <!-- <img class="rounded-lg-3" src="../assets/images/asset-2.jpeg" alt="" width="720" height="200"> -->

        <div id="myCarousel" class="carousel slide mb-6" data-bs-ride="carousel">
          <div class="carousel-indicators">
            <button type="button" data-bs-target="#myCarousel" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
            <button type="button" data-bs-target="#myCarousel" data-bs-slide-to="1" aria-label="Slide 2"></button>
            <button type="button" data-bs-target="#myCarousel" data-bs-slide-to="2" aria-label="Slide 3"></button>
            <button type="button" data-bs-target="#myCarousel" data-bs-slide-to="3" aria-label="Slide 4"></button>
            <button type="button" data-bs-target="#myCarousel" data-bs-slide-to="4" aria-label="Slide 5"></button>
            <button type="button" data-bs-target="#myCarousel" data-bs-slide-to="5" aria-label="Slide 6"></button>
          </div>
          <div class="carousel-inner">
            <div class="carousel-item active">
              <img class="bd-placeholder-img" width="100%" height="100%" src="../assets/images/asset-1.jpeg" aria-hidden="true" preserveAspectRatio="xMidYMid slice" focusable="false"><rect width="100%" height="100%" fill="var(--bs-secondary-color)"/>
            </div>
            <div class="carousel-item">
              <img class="bd-placeholder-img" width="100%" height="100%" src="../assets/images/asset-2.jpeg" aria-hidden="true" preserveAspectRatio="xMidYMid slice" focusable="false"><rect width="100%" height="100%" fill="var(--bs-secondary-color)"/>
            </div>
            <div class="carousel-item">
              <img class="bd-placeholder-img" width="100%" height="100%" src="../assets/images/asset-3.jpeg" aria-hidden="true" preserveAspectRatio="xMidYMid slice" focusable="false"><rect width="100%" height="100%" fill="var(--bs-secondary-color)"/>
            </div>
            <div class="carousel-item">
              <img class="bd-placeholder-img" width="100%" height="100%" src="../assets/images/asset-4.jpeg" aria-hidden="true" preserveAspectRatio="xMidYMid slice" focusable="false"><rect width="100%" height="100%" fill="var(--bs-secondary-color)"/>
            </div>
            <div class="carousel-item">
              <img class="bd-placeholder-img" width="100%" height="100%" src="../assets/images/asset-5.jpeg" aria-hidden="true" preserveAspectRatio="xMidYMid slice" focusable="false"><rect width="100%" height="100%" fill="var(--bs-secondary-color)"/>
            </div>
            <div class="carousel-item">
              <img class="bd-placeholder-img" width="100%" height="100%" src="../assets/images/asset-6.jpeg" aria-hidden="true" preserveAspectRatio="xMidYMid slice" focusable="false"><rect width="100%" height="100%" fill="var(--bs-secondary-color)"/>
            </div>
          </div>
          <button class="carousel-control-prev" type="button" data-bs-target="#myCarousel" data-bs-slide="prev">
            <span class="carousel-control-prev-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Previous</span>
          </button>
          <button class="carousel-control-next" type="button" data-bs-target="#myCarousel" data-bs-slide="next">
            <span class="carousel-control-next-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Next</span>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>
