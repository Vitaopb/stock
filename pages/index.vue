<template>
  <main>
    <!-- <div class="background"></div> -->
    <div class="blob">
      <svg viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
        <path
          fill="#e5e5e5"
          d="M42.4,-48.2C51.6,-33.2,53.3,-16.6,48.2,-5.1C43.1,6.4,31.1,12.7,21.9,19C12.7,25.3,6.4,31.5,-6,37.5C-18.4,43.5,-36.7,49.3,-50.1,43C-63.6,36.7,-72,18.4,-71.6,0.4C-71.2,-17.5,-61.8,-35,-48.4,-50C-35,-65,-17.5,-77.5,-0.5,-77.1C16.6,-76.6,33.2,-63.2,42.4,-48.2Z"
          transform="translate(100 100)"
        />
      </svg>
    </div>
    <div
      style="
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 5rem;
        height: 100%;
        width: 100%;
      "
    >
      <div class="part-one" style="width: 50%">
        <header>
          <h1>STOCK</h1>
          <p>
            Registre seus produtos e tenha o controle do estoque na palma de sua
            mão.
          </p>
        </header>
        <v-btn
          to="/auth/login"
          class="btn-login"
          color="#00bfa6"
          style="
            height: 3rem;
            width: 100%;
            margin: 1rem;
            text-transform: capitalize !important;
            color: #fff;
            font-weight: 800;
            font-size: 1.2rem;
          "
          >Login</v-btn
        >
      </div>
      <div class="part-two" style="width: 50%">
        <v-img src="./deliveryman.svg"></v-img>
      </div>
    </div>
  </main>
</template>

<script setup>
useHead({
  title: "Página Inicial",
});
definePageMeta({
  layout: "external",
});
</script>

<style lang="scss" scoped>
main {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
  width: 100%;
  background-image: url("../public/blob-wave.svg");
  background-repeat: no-repeat;
  background-size: cover;
  overflow:  hidden !important;
}

.part-one {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100%;
  width: 100%;
  padding: 5rem;

  h1 {
    font-size: 5rem;
    font-weight: 800;
    color: #00bfa6;
    -webkit-text-stroke: 5px #fff;
  }

  p {
    font-size: 1.5rem;
    font-weight: 500;
    color: #00bfa6;
  }
}

.blob {
  position: absolute;
  top: 0;
  left: 0;
  fill: #023f92;
  width: 40vmax;
  z-index: -1;
  animation: move 10s ease-in-out infinite;
  transform-origin: 50% 50%;
  overflow:  hidden !important;
}

@keyframes move {
  0% {
    transform: scale(1) translate(10px, -30px);
  }
  38% {
    transform: scale(0.8, 1) translate(80vw, 30vh) rotate(160deg);
  }
  40% {
    transform: scale(0.8, 1) translate(80vw, 30vh) rotate(160deg);
  }
  78% {
    transform: scale(1.3) translate(0vw, 30vh) rotate(-20deg);
  }
  80% {
    transform: scale(1.3) translate(0vw, 30vh) rotate(-20deg);
  }
  100% {
    transform: scale(1) translate(10px, -30px);
  }
}

@media (max-width: 768px) {
  .btn-login {
    padding:0 8rem;
  }
  .part-one {

    height: 100vh;


    h1 {
      -webkit-text-stroke: 0 !important;
    }
  }

  .part-two {
    display: none;
  }
}
</style>
