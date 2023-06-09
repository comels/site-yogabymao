<script setup>
import { ref } from "vue";
const isMenuOpen = ref(false);
</script>

<template>
  <nav class="mb-8 my-7">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between h-16">
        <!-- Logo -->
        <div class="flex-shrink-0 flex items-center">
          <router-link
            to="/"
            class="text-black text-3xl font-montserrat font-bold"
            ><img class="w-64 mr-1" src="../assets/logomao.png" alt=""
          /></router-link>
        </div>

        <!-- Menu Burger pour mobile -->
        <div class="flex items-center md:hidden">
          <button
            @click="isMenuOpen = !isMenuOpen"
            type="button"
            class="text-black focus:outline-none focus:ring-white"
          >
            <span class="sr-only">Toggle menu</span>
            <svg
              class="h-6 w-6"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h16M4 18h16"
              ></path>
            </svg>
          </button>
        </div>

        <!-- Liens de navigation -->
        <div class="hidden md:flex md:items-center md:space-x-4">
          <router-link
            to="/"
            class="text-black hover:font-medium px-3 py-2 rounded-md font-light"
            >HOME</router-link
          >
          <router-link
            to="/studio"
            class="text-black hover:font-medium px-3 py-2 rounded-md font-light"
            >LES COURS</router-link
          >
          <router-link
            to="/contact"
            class="text-black hover:font-medium px-3 py-2 rounded-md font-light"
            >CONTACT</router-link
          >
        </div>
      </div>
    </div>

    <!-- Menu déroulant mobile -->
    <div v-show="isMenuOpen" class="md:hidden">
      <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
        <router-link
          to="/"
          class="text-black hover:font-medium block pt-5 px-3 py-2 rounded-md font-light"
          @click="isMenuOpen = !isMenuOpen"
          >HOME</router-link
        >
        <router-link
          to="/studio"
          class="text-black hover:font-medium block px-3 py-2 rounded-md font-light"
          @click="isMenuOpen = !isMenuOpen"
          >LES COURS</router-link
        >
        <router-link
          to="/contact"
          class="text-black hover:font-medium block px-3 py-2 rounded-md font-light"
          @click="isMenuOpen = !isMenuOpen"
          >CONTACT</router-link
        >
      </div>
    </div>
  </nav>
</template>

<style lang="scss" scoped>
* {
  font-family: "Montserrat", sans-serif;
}
</style>
