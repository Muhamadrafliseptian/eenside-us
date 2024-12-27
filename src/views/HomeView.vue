<script setup>
import sound from '../assets/video/fall.mp3'
import dewa from '../assets/video/akumilikmu.mp3'
import edsheeran from '../assets/video/edsheeran.mp3'
import glenFred from '../assets/video/glen.mp3'
import rezaart from '../assets/video/reza.mp3'
import dewadua from '../assets/video/dewadua.mp3'
import { ref, onMounted } from 'vue';
import endahImage from '../assets/images/asset-1.jpeg'

const dewas = new Audio(dewa);
const jamesArthur = new Audio(sound);
const edSheeran = new Audio(edsheeran);
const glen = new Audio(glenFred);
const rezaArt = new Audio(rezaart);
const dewaDua = new Audio(dewadua);

const stopAllMusic = () => {
  [dewas, glen, edSheeran, jamesArthur, rezaArt, dewaDua].forEach((audio) => {
    audio.pause();
    audio.currentTime = 0; // Reset waktu pemutaran
  });
};

const playMusic = () => {
  stopAllMusic(); // Hentikan semua musik
  dewas.play(); // Mainkan lagu "Dewa"
};

const playMusicJames = () => {
  stopAllMusic(); // Hentikan semua musik
  jamesArthur.play(); // Mainkan lagu "James Arthur"
};

const stopMusicJamesArthur = () => {
  stopAllMusic(); // Hentikan semua musik
};

const playMusicGlen = () => {
  stopAllMusic(); // Hentikan semua musik
  glen.play(); // Mainkan lagu "Glen"
};

const stopMusicGlen = () => {
  stopAllMusic(); // Hentikan semua musik
};

const playEdSheeran = () => {
  stopAllMusic(); // Hentikan semua musik
  edSheeran.play(); // Mainkan lagu "Glen"
};

const stopEdSheeran = () => {
  stopAllMusic(); // Hentikan semua musik
};

const playReza = () => {
  stopAllMusic(); // Hentikan semua musik
  playReza.play(); // Mainkan lagu "Glen"
};

const stopRezaArt = () => {
  stopAllMusic(); // Hentikan semua musik
};

const playDewaDua = () => {
  stopAllMusic(); // Hentikan semua musik
  dewaDua.play(); // Mainkan lagu "Glen"
};

const stopDewaDua = () => {
  stopAllMusic(); // Hentikan semua musik
};
</script>

<style>
.carousel-inner .carousel-item img {
  width: 100%;
  height: 300px;
  object-fit: cover;
}

.carousel-inner .item-second img {
  width: 100%;
  height: 500px;
  object-fit: cover;
}

/* Responsif untuk tablet */
@media (max-width: 768px) {
  .carousel-inner .item-second img {
    height: 500px;
    /* Kurangi tinggi gambar untuk layar yang lebih kecil */
  }
}

/* Responsif untuk ponsel */
@media (max-width: 576px) {
  .carousel-inner .item-second img {
    height: 500px;
    /* Kurangi tinggi lebih jauh untuk ponsel */
  }
}
</style>

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
          Selamat! Udah berhasil menyelesaikan salah satu perjalanan panjang yang melelahkan. Semoga kelulusan ini akan
          menjadi pembuka dan selalu membawa kebaikan bagi kamu dan juga bagi siapapun yang ada di
          hidup kamu.
        </p>
        <div class="d-grid gap-2 d-md-flex justify-content-md-start mb-4 mb-lg-3">
          <button type="button" class="btn  btn-primary btn-lg px-4 me-md-2 fw-bold" @click="playMusic">
            <p class="text-light mt-0 mb-0">
              Pake Lagu Biar Asik
            </p>
          </button>
          <a href="#image" class="btn  btn-dark btn-lg px-4">
            <p class=" mt-0 mb-0 text-light">
              lanjut scroll dulu deh
            </p>
          </a>
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
              <img class="bd-placeholder-img" src="../assets/images/asset-2.jpeg" alt="Image 1">
            </div>
            <div class="carousel-item">
              <img class="bd-placeholder-img" src="../assets/images/asset-5.jpg" alt="Image 2">
            </div>
            <div class="carousel-item">
              <img class="bd-placeholder-img" src="../assets/images/asset-6.jpg" alt="Image 3">
            </div>
            <div class="carousel-item">
              <img class="bd-placeholder-img" src="../assets/images/asset-5.jpeg" alt="Image 4">
            </div>
            <div class="carousel-item">
              <img class="bd-placeholder-img" src="../assets/images/asset-3.jpeg" alt="Image 5">
            </div>
            <div class="carousel-item">
              <img class="bd-placeholder-img" src="../assets/images/asset-9.jpeg" alt="Image 6">
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

  <div class="container" id="image">
    <h1>Ah, Lucu banget!</h1>
    <div class="row row-cols-1 row-cols-md-3 g-4">
      <div class="col">
        <div class="card">
          <img src="../assets/images/asset-7.jpg" class="card-img-top" alt="...">
        </div>
      </div>
      <div class="col">
        <div class="card">
          <img src="../assets/images/asset-8.jpg" class="card-img-top" alt="...">
        </div>
      </div>
      <div class="col">
        <div class="card">
          <img src="../assets/images/asset-9.jpg" class="card-img-top" alt="...">
        </div>
      </div>
    </div>
  </div>

  <div class="container">
    <h2 class="text-center mb-4">Pilih dulu lagunya</h2>
    <div class="list-group mb-5">
      <div class="list-group-item d-flex justify-content-between align-items-center">
        <div>
          <strong>Falling Like The Star</strong>
          <p class="mb-0 text-muted">James Arthur</p>
        </div>
        <div>
          <button class="btn btn-primary btn-sm me-2" @click="playMusicJames()">
            ▶ Play
          </button>
          <button class="btn btn-danger btn-sm" @click="stopMusicJamesArthur()">
            ⏹ Stop
          </button>
        </div>
      </div>
    </div>

    <div class="list-group mb-5">
      <div class="list-group-item d-flex justify-content-between align-items-center">
        <div>
          <strong>Adu Rayu</strong>
          <p class="mb-0 text-muted">Tulus feat Glen</p>
        </div>
        <div>
          <button class="btn btn-primary btn-sm me-2" @click="playMusicGlen()">
            ▶ Play
          </button>
          <button class="btn btn-danger btn-sm" @click="stopMusicGlen()">
            ⏹ Stop
          </button>
        </div>
      </div>
    </div>

    <div class="list-group mb-5">
      <div class="list-group-item d-flex justify-content-between align-items-center">
        <div>
          <strong>Photograph</strong>
          <p class="mb-0 text-muted">Ed Sheeran</p>
        </div>
        <div>
          <button class="btn btn-primary btn-sm me-2" @click="playEdSheeran()">
            ▶ Play
          </button>
          <button class="btn btn-danger btn-sm" @click="stopEdSheeran()">
            ⏹ Stop
          </button>
        </div>
      </div>
    </div>

    <div class="list-group mb-5">
      <div class="list-group-item d-flex justify-content-between align-items-center">
        <div>
          <strong>Keabadian</strong>
          <p class="mb-0 text-muted">Reza Artamevia</p>
        </div>
        <div>
          <button class="btn btn-primary btn-sm me-2" @click="playReza()">
            ▶ Play
          </button>
          <button class="btn btn-danger btn-sm" @click="stopRezaArt()">
            ⏹ Stop
          </button>
        </div>
      </div>
    </div>

    <div class="list-group mb-5">
      <div class="list-group-item d-flex justify-content-between align-items-center">
        <div>
          <strong>Cintakan membawamu kembali</strong>
          <p class="mb-0 text-muted">Dewa 19 ft Virzha</p>
        </div>
        <div>
          <button class="btn btn-primary btn-sm me-2" @click="playDewaDua()">
            ▶ Play
          </button>
          <button class="btn btn-danger btn-sm" @click="stopDewaDua()">
            ⏹ Stop
          </button>
        </div>
      </div>
    </div>
  </div>

  <div class="container-fluid">
    <div class="row p-4 pb-0 pe-lg-0 pt-lg-5 align-items-center justify-content-center">
      <div class="col-lg-4">
        <div id="myCarouselSecond" class="carousel slide mb-6" data-bs-ride="carousel">
          <div class="carousel-indicators">
            <button type="button" data-bs-target="#myCarouselSecond" data-bs-slide-to="0" class="active"
              aria-current="true" aria-label="Slide 1"></button>
            <button type="button" data-bs-target="#myCarouselSecond" data-bs-slide-to="1" aria-label="Slide 2"></button>
            <button type="button" data-bs-target="#myCarouselSecond" data-bs-slide-to="2" aria-label="Slide 3"></button>
            <button type="button" data-bs-target="#myCarouselSecond" data-bs-slide-to="3" aria-label="Slide 5"></button>
            <button type="button" data-bs-target="#myCarouselSecond" data-bs-slide-to="4" aria-label="Slide 5"></button>
            <button type="button" data-bs-target="#myCarouselSecond" data-bs-slide-to="5" aria-label="Slide 5"></button>
            <button type="button" data-bs-target="#myCarouselSecond" data-bs-slide-to="6" aria-label="Slide 5"></button>
            <button type="button" data-bs-target="#myCarouselSecond" data-bs-slide-to="7" aria-label="Slide 5"></button>
          </div>
          <div class="carousel-inner">
            <div class="carousel-item item-second active border-5">
              <img class="bd-placeholder-img" src="../assets/images/asset-10.jpeg" alt="Image 1">
            </div>
            <div class="carousel-item item-second">
              <img class="bd-placeholder-img" src="../assets/images/asset-13.jpeg" alt="Image 2">
            </div>
            <div class="carousel-item item-second">
              <img class="bd-placeholder-img" src="../assets/images/asset-14.jpeg" alt="Image 3">
            </div>
            <div class="carousel-item item-second">
              <img class="bd-placeholder-img" src="../assets/images/asset-17.jpeg" alt="Image 3">
            </div>


            <div class="carousel-item item-second">
              <img class="bd-placeholder-img" src="../assets/images/asset-15.jpeg" alt="Image 4 ">
            </div>
            <div class="carousel-item item-second">
              <img class="bd-placeholder-img" src="../assets/images/asset-16.jpeg" alt="Image 4 ">
            </div>
            <div class="carousel-item item-second">
              <img class="bd-placeholder-img" src="../assets/images/asset-11.jpeg" alt="Image 4 ">
            </div>
            <div class="carousel-item item-second">
              <img class="bd-placeholder-img" src="../assets/images/asset-12.jpeg" alt="Image 4 ">
            </div>
          </div>
          <button class="carousel-control-prev" type="button" data-bs-target="#myCarouselSecond" data-bs-slide="prev">
            <span class="carousel-control-prev-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Previous</span>
          </button>
          <button class="carousel-control-next" type="button" data-bs-target="#myCarouselSecond" data-bs-slide="next">
            <span class="carousel-control-next-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Next</span>
          </button>
        </div>
      </div>
      <div class="col-lg-7 p-3 p-lg-5 pt-lg-3 ">
        <h2 class="display-4 fw-bold lh-1  text-dark">
          How've <span class="border-bottom text-primary border-5 border-primary">We Started</span><span
            class="text-warning">!</span>
        </h2>
        <p class="text-dark mt-5">
          Kayaknya ini bakal terlalu panjang untuk diceritain di sini, tapi gapapa, aku sedikit cerita tentang
          perjalanan kita. Aku dan kamu saling tau satu sama lain saat SMA, sekitar 6 tahun lalu. kamu adalah sebab
          jatuh cinta pertamaku dengan hati, ga ada sebab dan alasan yang pasti kenapa aku bisa suka ke kamu. Saat itu,
          aku ngga sadar bahwa komunikasi aku ke kamu itu belum baik, aku masih jadi orang yang selalu berkata lalu
          berpikir.
        </p>

        <p class="text-dark mt-5">
          At the short time, kita lulus dari SMA. kamu melanjutkan kuliah di Jakarta. Sedangkan aku kuliah di Indramayu,
          kita pisah, kita jauh, kita beda 192 kilometer. Di tahun pertama kuliah, hati aku kayak masih tertinggal di
          kamu.
          Tapi, aku sadar bahwa kita emang ngga bisa dipaksakan untuk benar-benar jadi satu. Aku mulai buka hati dengan
          perempuan lain, dan kamu pun juga sebaliknya. Saat kamu ngasih tau kalo kamu ditembak, aku seneng sekaligus
          cukup sedih. Seneng karena akhirnya kamu bisa buka hati untuk pria lain, di satu sisi lainnya sedih karena
          rasa aku ke kamu harus kupaksa lenyap. Dan, akhirnya kita engga komunikasi selama 2 tahun.
        </p>

        <p class="text-dark mt-5">
          Kamu putus, lalu balikan, dan putus lagi. Aku juga masih mengusahakan hatiku untuk yang perempuan lain juga.
          Tapi, setelah kamu putus di bulan Mei 2024, aku bener-bener ga mau kehilangan kamu untuk kedua kalinya. Aku
          merasa udah
          cukup yakin untuk mengusahakan apa yang aku bisa kuusahain untuk kamu. dan, aku merasa ini adalah jatuh cinta
          paling berkesan dalam kehidupan aku.
          Kamu punya tempat spesial di hati aku. sehat-sehat selalu. semoga aku bisa jadi rumah buat kamu, menjadi
          tempat paling aman dan nyaman saat kamu butuh cerita, menjadi tempat ketika kamu butuh rasa dicintai. Love u
          at every moment!

        </p>
      </div>
    </div>
  </div>


</template>