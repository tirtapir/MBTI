<template>
  <div
    class="w-100 flex flex-col flex-wrap items-center justify-around mx-auto pb-8"
  >
    <h1 class="pb-2 text-lg font-medium leading-8 text-white">
      Hasil analisa rekomendasi jurusan yang cocok untukmu
    </h1>
    <div class="h- w-48 bg-[#E7C8FA] rounded-full"></div>
    <div
      class="flex justify-center items-center h-44 w-96 bg-white/25 rounded-xl my-4"
    >
      <h1 class="text-white text-6xl">{{ data.tipe }}</h1>
    </div>
    <h2 class="w-1/2 text-center text-white my-6">
      {{ data.deskripsi }}
    </h2>

    <div class="w-1/2 mx-auto">
      <p class="mb-1 text-xl font-medium text-white">Introvert</p>
      <div class="h-6 mb-4 bg-gray-200 rounded-full">

        <div class="h-6 bg-[#ED9393] rounded-full text-white font-semibold text-md text-center" style="width: 66%"> 66%</div>
      </div>
    </div>

    <div class="w-1/2 mx-auto">
      <p class="mb-1 text-xl font-medium text-white">Intuition</p>
      <div class="h-6 mb-4 bg-gray-200 rounded-full">
        <div class="h-6 bg-[#ED9393] rounded-full text-white font-semibold text-md text-center" style="width: 62%">62%</div>
      </div>
    </div>

    <div class="w-1/2 mx-auto">
      <p class="mb-1 text-xl font-medium text-white">Thinking</p>
      <div class="h-6 mb-4 bg-gray-200 rounded-full">
        <div class="h-6 bg-[#ED9393] rounded-full text-white font-semibold text-md text-center" style="width: 62%">62%</div>
      </div>
    </div>

    <div class="w-1/2 mx-auto">
      <p class="mb-1 text-xl font-medium text-white">Prospecting</p>
      <div class="h-6 mb-4 bg-gray-200 rounded-full">
        <div class="h-6 bg-[#ED9393] rounded-full text-white font-semibold text-md text-center" style="width: 91%">91%</div>
      </div>
    </div>

    <h2 class="text-white text-lg font-medium my-4">Rekomendasi Jurusan</h2>
    <div class="w-1/2 text-center">
      <h2 class="text-white font-normal">{{ data.jurusan }}</h2>
    </div>

    <nuxt-link to="">
      <button
        class="text-white font-medium mt-4 h-12 w-48 bg-gradient-to-r from-[#726BA7] to-[#2B2759] rounded-lg border border-[#E7C8FA] opacity-70 drop-shadow-lg flex flex-wrap items-center justify-around mx-auto"
      >
        Unduh
      </button>
    </nuxt-link>
  </div>
</template>

<script setup>
const data = {
  deskripsi:
    "Seorang Ahli Logika (INTP) adalah seseorang dengan ciri-ciri kepribadian Introvert, Intuitif, Berpikir, dan Prospek. Para pemikir fleksibel ini senang mengambil pendekatan yang tidak konvensional dalam banyak aspek kehidupan. Mereka sering mencari jalan yang tidak terduga, memadukan kemauan untuk bereksperimen dengan kreativitas pribadi.",
  tipe: "INTP",
  jurusan:
    "Fisika, Forensik, Ilmu Komputer, Hukum, Teknik informatika, Sistem Informasi, Ilmu Politik, Fotografi,  Sastra",
};
</script>
