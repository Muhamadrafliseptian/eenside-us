<script setup>
import sound from '../assets/video/katakan.mp3'
import { ref, onMounted } from 'vue';
import endahImage from '../assets/images/asset-1.jpeg'

const audio = new Audio(sound);

const playMusic = () => {
  audio.play();
};

const countdown = ref({
  days: 0,
  hours: 0,
  minutes: 0,
  seconds: 0,
});

const targetDate = new Date('2024-12-28T00:00:00+07:00');

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

onMounted(() => {
  updateCountdown();
  setInterval(updateCountdown, 1000);
});
</script>

<template>
  <div class="container-fluid my-5" :style="{
    backgroundImage: `linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url(${endahImage})`,
    backgroundSize: 'cover',
    backgroundPosition: 'center',
    backgroundRepeat: 'no-repeat'
  }">
    <div class="row p-4 pb-0 pe-lg-0 pt-lg-5 align-items-center justify-content-center">
      <div class="col-lg-7 p-3 p-lg-5 pt-lg-3 ">
        <h2 class="display-4 fw-bold lh-1  text-light">
          Happy <span class="border-bottom text-warning border-5 border-warning">Graduation</span>!
        </h2>
        <p class="lead text-light fw-bold mt-5">
          {{ countdown.days }} Hari
          {{ countdown.hours }} Jam
          {{ countdown.minutes }} Menit
          {{ countdown.seconds }} Detik
        </p>
        <div class="d-grid gap-2 d-md-flex justify-content-md-start mb-4 mb-lg-3">
          <button type="button" class="btn  btn-primary btn-lg px-4 me-md-2 fw-bold" @click="playMusic">
            <p class="text-light mt-0 mb-0">
              Pake Lagu Biar Asik
            </p>
          </button>
          <button type="button" class="btn  btn-dark btn-lg px-4">
            <p class=" mt-0 mb-0 text-light">
              Klik nanti muncul quotes
            </p>
          </button>
        </div>
      </div>
      <div class="col-lg-4">
        <div id="myCarousel" class="carousel slide mb-6" data-bs-ride="carousel">
          <div class="carousel-indicators">
            <button type="button" data-bs-target="#myCarousel" data-bs-slide-to="0" class="active" aria-current="true"
              aria-label="Slide 1"></button>
            <button type="button" data-bs-target="#myCarousel" data-bs-slide-to="1" aria-label="Slide 2"></button>
            <button type="button" data-bs-target="#myCarousel" data-bs-slide-to="2" aria-label="Slide 3"></button>
            <button type="button" data-bs-target="#myCarousel" data-bs-slide-to="3" aria-label="Slide 4"></button>
            <button type="button" data-bs-target="#myCarousel" data-bs-slide-to="4" aria-label="Slide 5"></button>
            <button type="button" data-bs-target="#myCarousel" data-bs-slide-to="5" aria-label="Slide 6"></button>
          </div>
          <div class="carousel-inner">
            <div class="carousel-item active border-5">
              <img class="bd-placeholder-img" width="100%" height="100%" src="../assets/images/asset-1.jpeg"
                aria-hidden="true" preserveAspectRatio="xMidYMid slice" focusable="false">
              <rect width="100%" height="100%" fill="var(--bs-secondary-color)" />
            </div>
            <div class="carousel-item">
              <img class="bd-placeholder-img" width="100%" height="100%" src="../assets/images/asset-1.jpeg"
                aria-hidden="true" preserveAspectRatio="xMidYMid slice" focusable="false">
              <rect width="100%" height="100%" fill="var(--bs-secondary-color)" />
            </div>
            <div class="carousel-item">
              <img class="bd-placeholder-img" width="100%" height="100%" src="../assets/images/asset-1.jpeg"
                aria-hidden="true" preserveAspectRatio="xMidYMid slice" focusable="false">
              <rect width="100%" height="100%" fill="var(--bs-secondary-color)" />
            </div>
            <div class="carousel-item">
              <img class="bd-placeholder-img" width="100%" height="100%" src="../assets/images/asset-1.jpeg"
                aria-hidden="true" preserveAspectRatio="xMidYMid slice" focusable="false">
              <rect width="100%" height="100%" fill="var(--bs-secondary-color)" />
            </div>
            <div class="carousel-item">
              <img class="bd-placeholder-img" width="100%" height="100%" src="../assets/images/asset-1.jpeg"
                aria-hidden="true" preserveAspectRatio="xMidYMid slice" focusable="false">
              <rect width="100%" height="100%" fill="var(--bs-secondary-color)" />
            </div>
            <div class="carousel-item">
              <img class="bd-placeholder-img" width="100%" height="100%" src="../assets/images/asset-1.jpeg"
                aria-hidden="true" preserveAspectRatio="xMidYMid slice" focusable="false">
              <rect width="100%" height="100%" fill="var(--bs-secondary-color)" />
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

  <div class="container px-4 py-5" id="custom-cards">
    <h2 class="pb-2 border-bottom">Ini Text Juga</h2>

    <div class="row row-cols-1 row-cols-lg-3 align-items-stretch g-4 py-5">
      <div class="col">
        <div class="card card-cover h-100 w-100 text-bg-dark overflow-hidden rounded-4 shadow-lg" :style="{
          backgroundImage: `url(${endahImage})`,
          backgroundSize: 'contain',
          backgroundPosition: 'center',
          backgroundRepeat: 'no-repeat'
        }">
          <div class="d-flex flex-column h-100 p-5 pb-3 text-white text-shadow-1">
            <h3 class="d-flex flex-column h-100 p-5 pb-3 text-white text-shadow-1">Another longer title belongs here
            </h3>
            <ul class="d-flex list-unstyled mt-auto">
              <li class="me-auto">
                <img src="../assets/images/asset-1.jpeg" alt="Bootstrap" width="32" height="32"
                  class="rounded-circle border border-white">
              </li>
            </ul>
          </div>
        </div>
      </div>

      <div class="col">
        <div class="card card-cover h-100 w-100 text-bg-dark overflow-hidden rounded-4 shadow-lg" :style="{
          backgroundImage: `url(${endahImage})`,
          backgroundSize: 'contain',
          backgroundPosition: 'center',
          backgroundRepeat: 'no-repeat'
        }">
          <div class="d-flex flex-column h-100 p-5 pb-3 text-white text-shadow-1">
            <h3 class="d-flex flex-column h-100 p-5 pb-3 text-white text-shadow-1">Another longer title belongs here
            </h3>

            <ul class="d-flex list-unstyled mt-auto">
              <li class="me-auto">
                <img src="../assets/images/asset-1.jpeg" alt="Bootstrap" width="32" height="32"
                  class="rounded-circle border border-white">
              </li>
            </ul>
          </div>
        </div>
      </div>

      <div class="col">
        <div class="card card-cover h-100 overflow-hidden text-bg-dark rounded-4 shadow-lg" :style="{
          backgroundImage: `url(${endahImage})`,
          backgroundSize: 'contain',
          backgroundPosition: 'center',
          backgroundRepeat: 'no-repeat'
        }">
          <div class="d-flex flex-column h-100 p-5 pb-3 text-shadow-1">
            <h3 class="d-flex flex-column h-100 p-5 pb-3 text-white text-shadow-1">Another longer title belongs here
            </h3>
            <ul class="d-flex list-unstyled mt-auto">
              <li class="me-auto">
                <img src="../assets/images/asset-1.jpeg" alt="Bootstrap" width="32" height="32"
                  class="rounded-circle border border-white">
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<!-- <img class="rounded-lg-3" src="../assets/images/asset-2.jpeg" alt="" width="720" height="200"> -->
