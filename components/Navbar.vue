<template>
  <nav
    class="w-full h-20 dark:bg-gray-800 bg-white flex justify-center items-center border-b shadow-sm"
  >
    <div
      class="xl:mx-auto container w-full h-full flex items-center flex-wrap justify-between px-4"
    >
      <NuxtLink class="font-bold w-1/4s text-3xl dark:text-white text-gray-800"
        >MSK</NuxtLink
      >

      <div class="hidden">
        <button
          class="hamburger flex items-center hover:bg-gray-100 p-2 rounded-full cursor-pointer"
          aria-controls="mobile-menu"
          aria-expanded="false"
        >
          <!--        close hamburger-->
          <svg
            v-if="!toggleVisibility"
            xmlns="http://www.w3.org/2000/svg"
            class="h-6 w-6 open-hamburger"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
            stroke-width="2"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M4 6h16M4 12h16M4 18h16"
            />
          </svg>
          <svg
            v-if="toggleVisibility"
            xmlns="http://www.w3.org/2000/svg"
            class="h-6 w-6 close-hamburger"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
            stroke-width="2"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M6 18L18 6M6 6l12 12"
            />
          </svg>
        </button>
      </div>
      <ul class="flex items-center space-x-5">
        <li class="">
          <nuxt-link
            class="text-sm text-white leading-none bg-primary dark:bg-dark py-2 px-4 hover:shadow-2xl shadow-sm cursor-pointer rounded-lg"
            to="#"
            >Create</nuxt-link
          >
        </li>
        <li class="relative">
          <button
            @click="handleMenu"
            id="user-menu-button"
            aria-expanded="false"
            type="button"
            data-dropdown-toggle="dropdown"
            class="avatar-wrapper flex items-center space-x-2 cursor-pointer dark:text-dark"
          >
            <span class="sr-only">Open user menu</span>
            <Avatar src="https://picsum.photos/200" avatarLocation="navbar" />
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-3 w-3"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
              stroke-width="2"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M19 9l-7 7-7-7"
              />
            </svg>
          </button>
          <!-- Dropdown menu -->
          <div
            v-if="toggleVisibility"
            class="z-50 hiddens right-0 -mr-4 absolute my-4 text-base list-none bg-white rounded divide-y divide-gray-100 shadow bg-primary dark:bg-gray-700 dark:divide-white"
            id="dropdown"
          >
            <div class="py-3 px-4">
              <span class="block text-sm text-white dark:text-white"
                >Bonnie Green</span
              >
              <span
                class="block text-sm font-medium text-white truncate dark:text-dark"
                >name@flowbite.com</span
              >
            </div>
            <ul class="py-1" aria-labelledby="dropdown">
              <li>
                <a
                  href="#"
                  class="block py-2 px-4 text-sm text-white hover:bg-dark dark:hover:bg-gray-600 dark:text-gray-200 dark:hover:text-white"
                  >Profile</a
                >
              </li>
              <li>
                <a
                  href="#"
                  class="block py-2 px-4 text-sm text-white hover:bg-dark dark:hover:bg-gray-600 dark:text-gray-200 dark:hover:text-white"
                  >Sign out</a
                >
              </li>
            </ul>
          </div>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script setup lang="ts">
import { ref } from "vue";

const toggleVisibility = ref(false);
const handleMenu = () => {
  toggleVisibility.value = !toggleVisibility.value;
};
</script>

<style scoped></style>
