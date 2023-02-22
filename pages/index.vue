<template>
  <main
    style="
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100%;
      width: 100%;
    "
  >
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
      <div style="width: 50%">
        <v-img src="./deliveryman.svg"></v-img>
      </div>
    </div>
  </main>
</template>

<script setup>

useHead({
  title: 'Página Inicial',
})
definePageMeta({
  layout: 'external',
})
</script>

<style lang="scss" scoped>
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
  }

  p {
    font-size: 1.5rem;
    font-weight: 500;
    color: #00bfa6;
  }
}
</style>
