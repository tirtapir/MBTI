<template>
  <nav class="bg-transparent border-gray-200 dark:bg-white max-w-screen-xl flex flex-wrap  items-center justify-around mx-auto p-4 ">
    <div
      class="max-w-screen-xl flex flex-wrap items-center justify-between mx-auto p-4"
    >
      <button
        data-collapse-toggle="navbar-default"
        type="button"
        class="inline-flex items-center p-2 w-10 h-10 justify-center text-sm text-white rounded-lg md:hidden hover:bg-[#E8C7FA] dark:text-gray-400 dark:hover:bg-gray-700 dark:focus:ring-gray-600"
        aria-controls="navbar-default"
        aria-expanded="false"
      >
        <span class="sr-only">Open main menu</span>
        <svg
          class="w-5 h-5"
          aria-hidden="true"
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 17 14"
        >
          <path
            stroke="currentColor"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M1 1h15M1 7h15M1 13h15"
          />
        </svg>
      </button>
      <div class="hidden w-full md:block md:w-auto" id="navbar-default">
        <ul
          class="font-medium flex flex-col p-4 md:p-0 mt-4 border border-gray-10 rounded-lg bg-[#e1a8ed] md:flex-row md:items-center md:space-x-28 md:mt-0 md:border-0 md:bg-transparent dark:bg-gray-800 md:dark:bg-white dark:border-gray-700"
        >
          <li>
            <nuxt-link
              to="/"
              class="block py-2 pl-3 pr-4 text-white rounded hover:bg-[#E8C7FA] md:hover:bg-transparent md:border-0 md:hover:text-[#E8C7FA] md:p-0 dark:text-white md:dark:hover:text-[#E8C7FA] dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent"
              aria-current="page"
              >Home</nuxt-link
            >
          </li>
          <li>
            <nuxt-link
              to="/kepribadian"
              class="block py-2 pl-3 pr-4 text-white rounded hover:bg-[#E8C7FA] md:hover:bg-transparent md:border-0 md:hover:text-[#E8C7FA] md:p-0 dark:text-white md:dark:hover:text-[#E8C7FA] dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent"
              >Kepribadian</nuxt-link
            >
          </li>
          <li>
            <nuxt-link
              to="/jurusan"
              class="block py-2 pl-3 pr-4 text-white rounded hover:bg-[#E8C7FA] md:hover:bg-transparent md:border-0 md:hover:text-[#E8C7FA] md:p-0 dark:text-white md:dark:hover:text-[#E8C7FA] dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent"
              >Jurusan</nuxt-link
            >
          </li>
          <img src="/image/planet.svg" w- alt="">
          <li>
            <nuxt-link
              to="/sumber"
              class="block py-2 pl-3 pr-4 text-white rounded hover:bg-[#E8C7FA] md:hover:bg-transparent md:border-0 md:hover:text-[#E8C7FA] md:p-0 dark:text-white md:dark:hover:text-[#E8C7FA] dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent"
              >Sumber</nuxt-link
            >
          </li>
          <li>
            <nuxt-link
              to="/tentang"
              class="block py-2 pl-3 pr-4 text-white rounded hover:bg-[#E8C7FA] md:hover:bg-transparent md:border-0 md:hover:text-[#E8C7FA] md:p-0 dark:text-white md:dark:hover:text-[#E8C7FA] dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent"
              >Tentang</nuxt-link
            >
          </li>
          <li>
            <nuxt-link
              to="/kontak"
              class="block py-2 pl-3 pr-4 text-white rounded hover:bg-[#E8C7FA] md:hover:bg-transparent md:border-0 md:hover:text-[#E8C7FA] md:p-0 dark:text-white md:dark:hover:text-[#E8C7FA] dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent"
              >Kontak</nuxt-link
            >
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { onMounted } from "vue";
import { initFlowbite } from "flowbite";

// initialize components based on data attribute selectors
onMounted(() => {
  initFlowbite();
});
</script>

<style></style>
