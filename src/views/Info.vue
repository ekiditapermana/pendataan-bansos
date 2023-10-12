<template>
  <v-container class="text-center" v-if="this.$route.params.savedForm">
    <div class="header">
      <div>
        <v-banner color="blue" lines="two" max-width="800"
          ><v-icon slot="icon" color="black" size="48"
            >mdi-package-variant</v-icon
          >
          <v-banner-text class="text-left">
            <h2>Pendataan Bantuan Sosial Kemensos</h2>
          </v-banner-text>
        </v-banner>
      </div>
    </div>
    <v-card
      class="mx-auto px-7 py-10 rounded-b-lg rounded-t-0"
      max-width="800"
      outlined
      elevation="3"
    >
      <h1 class="text-headline success--text">
        Selamat, Data Berhasil Terkirim!
      </h1>

      <v-divider class="my-2"></v-divider>

      <p>
        Untuk menambahkan Data baru klik tombol dibawah ini
      </p>
      <v-btn rounded color="success" class="rounded-pill px-16 py-6" to="/">
        Tambah Data Baru
      </v-btn>
    </v-card>
  </v-container>
</template>

<script>
export default {
  beforeCreate() {
    if (!this.$route.params.savedForm) {
      document.title = this.$route.meta.title;
      this.$router.push("/");
    } else {
      document.title = "Berhasil disimpan";
    }
  },
};
</script>
