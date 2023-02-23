<template>
  <div
    style="
      width: 100%;
      height: 100vh;
      display: flex;
      justify-content: center;
      background-color: #e5e5e5;
      align-items: center;
    "
  >
    <div class="d-flex align-center justify-center w-100">
      <div style="width: 50%; padding: 5rem">
        <v-img height="400px" src="../auth.svg"></v-img>
      </div>
      <div style="width: 50%; margin: auto">
        <v-card color="whitesmoke" max-width="600px" width="100%">
          <header class="d-flex align-center mx-5 mt-6 justify-center">
            <h2 style="font-weight: 800; font-size: 1.6rem">STOCK</h2>
            <v-icon size="40">mdi-package-variant-closed</v-icon>
          </header>
          <div class="pa-6">
            <v-row class="pa-7 px-10">
              <v-col cols="12">
                <h2 style="font-weight: 800; margin-bottom: 10px">Login</h2>
                <v-text-field
                  v-model="email"
                  label="Email"
                  variant="underlined"
                  append-inner-icon="mdi-email"
                  type="email"
                  color="#00bfa6"
                  :rules="[(v) => !!v || 'Email é obrigatório']"
                ></v-text-field>
              </v-col>
              <v-col cols="12">
                <v-text-field
                  v-model="password"
                  label="Senha"
                  dense
                  color="#00bfa6"
                  variant="underlined"
                  :append-inner-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
                  @click:append="showPassword = !showPassword"
                  :type="showPassword ? 'text' : 'password'"
                  :rules="[(v) => !!v || 'Senha é obrigatória']"
                ></v-text-field>
                <div class="d-flex justify-end">
                  <p class="mr-1">Esqueceu sua senha?</p>
                  <a
                    @click="$router.push('/auth/forgotPassword')"
                    style="
                      text-decoration: underline #00bfa6;
                      color: #00bfa6;
                      cursor: pointer;
                    "
                    >Clique aqui</a
                  >
                </div>
              </v-col>
              <v-col cols="12">
                <v-btn
                  color="#00bfa6"
                  :loading="loading"
                  class="btn-login"
                  @click="login"
                  style="
                    width: 100%;
                    font-weight: 700;
                    color: #fff;
                    margin-bottom: 15px;
                  "
                >
                  Entrar
                </v-btn>
                <v-btn
                  class="btn-register"
                  @click="$router.push('/auth/register')"
                  variant="outlined"
                  style="
                    width: 100%;
                    font-weight: 700;
                    color: #00bfa6;
                    border: 2px solid #00bfa6;
                  "
                  color="#00bfa6"
                >
                  Registre-se
                </v-btn>
              </v-col>
            </v-row>
          </div>
        </v-card>
      </div>
    </div>
  </div>
</template>

<script setup>
definePageMeta({
  layout: "external",
});

useHead({
  title: "Login",
});

const email = ref("");
const password = ref("");
const loading = ref(false);
const showPassword = ref(false);

// Methods
const login = () => {
  if (email.value === "" || password.value === "") {
    return;
  }
  loading.value = true;
  $router.push("/dash");
};
</script>

<style lang="scss" scoped>
.btn-register:hover {
  background-color: #00bfa6 !important;
  color: #fff !important;
}

.btn-login:hover {
  background-color: transparent !important;
  color: #00bfa6 !important;
  border: 2px solid #00bfa6 !important;
}

@media screen {
  
}
</style>
