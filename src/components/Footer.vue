<script setup>
import { RouterLink } from "vue-router";
import { Icon } from "@iconify/vue";
</script>

<template>
  <footer class="dark:bg-gray-900 m-4">
    <div class="w-full max-w-screen-xl mx-auto p-4 md:py-8">
      <div class="flex items-center justify-end">
        <ul
          class="flex flex-wrap items-center mb-6 text-sm font-light text-black sm:mb-0 dark:text-gray-400"
        >
          <li class="mr-5">
            <a
              href="https://www.instagram.com/yogabymao/?hl=fr"
              target="_blank"
              rel="noopener noreferrer"
              ><Icon icon="mdi:instagram" color="#776a2e" width="40"
            /></a>
          </li>
          <li>
            <RouterLink class="hover:font-medium" to="/contact"
              >CONTACT</RouterLink
            >
          </li>
        </ul>
      </div>
      <!-- <hr
        class="my-6 border-gray-200 sm:mx-auto dark:border-gray-700 lg:my-8"
      />
      <span class="flex justify-center dark:text-gray-400"
        ><img class="w-64" src="../assets/logomao.png" alt=""
      /></span> -->
    </div>
  </footer>
</template>

<style lang="scss" scoped></style>
