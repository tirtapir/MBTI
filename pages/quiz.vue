<template>
  <div>
    <section v-if="isQuiz == true">
      <div class="m-24 bg-white/10 p-10 px-6 shadow-xl ring-1 ring-gray-900/5 sm:mx-auto sm:max-w-2xl sm:rounded-lg sm:px-4">
        <div class="mx-auto flex max-w-xl space-x-2">
          <div class="flex-none text-white text-base font-medium">
            <p>{{ questionNumber }} -></p>
          </div>
          <div class="text-white text-base font-medium">
            {{
              questions[
                questions.findIndex((el) => el.number == questionNumber)
              ].question  
            }}
            <input
              type="text"
              class="pl-0 mt-4 w-full placeholder-white/70 bg-transparent border-none text-white"
              placeholder="Ketik jawabanmu di sini . . ."
              v-model="answer"
            />
            <div class="h-1 bg-[#E7C8FA] w-full rounded-xl"></div>
            <nuxt-link to="/result">
              <button
              class="m-4 h-12 w-36 bg-gradient-to-r from-[#726BA7] to-[#2B2759] rounded-lg border border-[#E7C8FA] opacity-70 drop-shadow-lg flex flex-wrap items-center justify-around mx-auto"
              v-if="questionNumber == 12"
              @click="finishQuestion"
            >
              Selesai
            </button>  
            </nuxt-link>
            <button
              class="h-12 w-36 bg-gradient-to-r from-[#726BA7] to-[#2B2759] rounded-lg border border-[#E7C8FA] opacity-70 drop-shadow-lg mx-auto m-4"
              v-if="questionNumber < 12"
              @click="nextQuestion"
            >
              Next
            </button>
          </div>
        </div>
      </div>
    </section>

    <section
      class="w-full grid place-items-center mt-20"
      v-if="isQuiz == false"
    >
      <p
        class="text-2xl text-white font-semibold leading-8 text-center mb-7 mt-4"
      >
        Hai, Kami berupaya untuk memberikan rekomendasi jurusan <br />
        kuliah yang cocok dengan menganalisa kepribadianmu. <br />

        <br />Oleh karena itu, mohon jawab seluruh pertanyaan yang akan <br />
        kami berikan dengan jujur dan tanpa tekanan Ya !
      </p>
      <p
        class="text-white leading-10 font-medium text-2xl opacity-75 text-center mb-16"
      >
        Ini akan memakan waktu tidak lebih dari 5 menit
      </p>
      <button
        class="h-12 w-48 bg-gradient-to-r from-[#726BA7] to-[#2B2759] rounded-lg border border-[#E7C8FA] opacity-70 drop-shadow-lg flex flex-wrap items-center justify-around mx-auto"
        @click="isQuiz = true"
      >
        <span class="relative px-5 py-2.5 text-white text-base font-semibold">
          setuju
        </span>
      </button>
    </section>
  </div>
</template>

<script setup>
import { ref } from "vue";

const isQuiz = ref(false);
const questionNumber = ref(1);
const answer = ref("");
const allAnswer = ref([]);

const questions = ref([
  {
    number: 1,
    question:
      "Jika kamu diminta untuk memulai sebuah pertemuan dengan seseorang ataupun beberapa orang baru yang sebelumnya belum kamu kenal, apa yang akan kamu lakukan ?",
    type: "IE",
  },
  {
    number: 2,
    question:
      "Di luar rutinitas wajib seperti sekolah dan sebagainya, bagaimana biasanya kamu menghabiskan waktu untuk mendapatkan energi (kesenangan, ketenangan, mood), ceritakan seperti apa?",
    type: "IE",
  },
  {
    number: 3,
    question:
      "Jika kamu memiliki sebuah tujuan/rencana, apakah kamu lebih suka untuk membagikan hal tersebut kepada orang umum/publik (cth : media sosial) atau hanya kepada orang-orang tertentu? Dan seberapa sering kamu akan membagikannya?",
    type: "IE",
  },
  {
    number: 4,
    question:
      "Bagaimana cara kamu menangkap sebuah informasi baru dari seseorang yang dekat denganmu sekalipun ?",
    type: "SN",
  },
  {
    number: 5,
    question:
      "Bagaimana kamu melihat kegagalan atau kesalahan? Apakah cenderung mencari kesalahan dan menyalahkan hal yang tidak sesuai atau melihatnya sebagai kesempatan untuk belajar untuk meningkatkan keterampilan?",
    type: "SN",
  },
  {
    number: 6,
    question:
      "Jika guru memberikan tawaran lomba dalam bidang yang belum kamu kuasai dan bersedia memberi fasilitas mentor sebagai persiapan lomba itu, bagaimana cara kamu menyikapinya?",
    type: "SN",
  },
  {
    number: 7,
    question:
      "Ketika waktu ujian tersisa 30 menit, dan kamu telah menyelesaikan ujian tersebut lebih dahulu daripada teman temanmu, apa yang akan kamu lakukan? Apakah mengumpulkan terlebih dahulu, atau menunggu teman-teman yang lain selesai menjawab seluruh pertanyaan?",
    type: "TF",
  },
  {
    number: 8,
    question:
      "Jika dalam sebuah kelompok kerja kamu, terdapat satu teman kamu yang pasif dan cenderung lalai dengan tugasnya, apa yang akan kamu lakukan? Menegurnya atau mengambil alih tugasnya?",
    type: "TF",
  },
  {
    number: 9,
    question:
      "Jika sahabat kamu terlibat konflik karena kesalahannya, apakah kamu berupaya mencari solusi untuk membantunya meskipun ia salah atau menegaskan bahwa ia tetap salah dan menyuruhnya untuk menerima konsekuensinya?",
    type: "TF",
  },
  {
    number: 10,
    question:
      "Bagaimana cara kamu merencanakan kegiatan sehari-hari? Apakah lebih cenderung membuat jadwal yang tersusun rapi atau lebih fleksibel bergantung pada situasi?",
    type: "JP",
  },
  {
    number: 11,
    question:
      "Ketika kamu diharuskan memilih jam kegiatan non akademis, apakah kamu lebih nyaman untuk memilih jadwal di luar jam pelajaran atau pada saat jam pelajaran berlangsung?",
    type: "JP",
  },
  {
    number: 12,
    question:
      "Ketika ada PR yang harus diselesaikan malam ini, Tiba-tiba teman lamamu mengajak kamu untuk bertemu (reuni,bermain, ngobrol). Bagaimana cara kamu menyikapinya? , ceritakan alasannya!",
    type: "JP",
  },
]);

const nextQuestion = function () {
  questionNumber.value++;
  // alert(`Your answer is: ${answer.value}`);
  allAnswer.value.push(answer.value);
  answer.value = "";
};

const finishQuestion = function () {
  allAnswer.value.push(answer.value);
  alert(`Semua pertanyaan terpenuhi ${allAnswer.value}`);
};
</script>
