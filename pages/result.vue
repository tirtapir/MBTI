<template>
  <div>
    <section v-if="isResult == false">
      <div class="">
        <p class="text-white text-2xl font-semibold text-center my-12">
          Fyuhh... Setelah menyelasaikan beberapa kuesioner, akhirnya <br />
          selesai juga. Hasil rekomendasi kamu akan ditunjukkan di <br />
          halaman selanjutnya.<br />
        </p>
        <p class="text-white text-xl font-semibold opacity-70 text-center mb-6">
          Catatan
        </p>
        <p class="text-white text-xl font-normal opacity-70 text-center">
          Hasil yang akan ditampilkan merupakan hasil dari proses analisa kami
          melalui <br />
          kepribadian kamu untuk saat ini. Apabila jurusan yang kami
          rekomendasikan tidak <br />
          sesuai dengan yang kamu inginkan, Kamu bisa mengikuti panduan
          kepribadian untuk <br />
          menuju ke jurusan yang kamu inginkan
        </p>
      </div>
      <div class="my-8">
        <nuxt-link to="/postquiz">
          <button
            class="h-12 w-48 bg-gradient-to-r from-[#726BA7] to-[#2B2759] rounded-lg border border-[#E7C8FA] opacity-70 drop-shadow-lg flex flex-wrap items-center justify-around mx-auto"
          >
            <span
              class="relative px-5 py-2.5 text-white text-base font-semibold"
            >
              Lihat
            </span>
          </button>
        </nuxt-link>
      </div>
    </section>

    <section v-if="isResult == true">
      <div></div>
    </section>
  </div>
</template>

<script setup>
// import { ref } from "vue";
const isResult = ref(false);
</script>
