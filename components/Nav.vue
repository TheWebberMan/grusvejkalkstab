<template>
  <Disclosure as="header" class="bg-white shadow mt-3" v-slot="{ open }">
    <div
      class="mx-auto max-w-7xl px-2 sm:px-4 lg:divide-y lg:divide-gray-200 lg:px-8"
    >
      <div class="relative flex h-16 justify-between">
        <div class="relative z-10 flex px-2 lg:px-0">
          <div class="flex flex-shrink-0 items-center mb-2">
            <h1>Støvfri-jordstabilisering</h1>
            <!-- indsæt logo her -->
            <img
              src="https://i.ibb.co/0KdRF98/Grusvej-logo-150x71px-1.png"
              alt="Grusvej-logo-150x71px-1"
              border="0"
            />
          </div>
        </div>
        <!-- <div
          class="relative z-0 flex flex-1 items-center justify-center px-2 sm:absolute sm:inset-0"
        >
          <div class="w-full sm:max-w-xs">
            <label for="search" class="sr-only">Search</label>
            <div class="relative">
              <div
                class="pointer-events-none absolute inset-y-0 left-0 flex items-center pl-3"
              >
                <MagnifyingGlassIcon
                  class="h-5 w-5 text-gray-400"
                  aria-hidden="true"
                />
              </div>
              <input
                id="search"
                name="search"
                class="block w-full rounded-md border-0 bg-white py-1.5 pl-10 pr-3 text-gray-900 ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
                placeholder="Search"
                type="search"
              />
            </div>
          </div>
        </div> -->
        <div class="relative z-10 flex items-center lg:hidden">
          <!-- Mobile menu button -->
          <DisclosureButton
            class="inline-flex items-center justify-center rounded-md p-2 text-gray-400 hover:bg-gray-100 hover:text-gray-500 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-indigo-500"
          >
            <span class="sr-only">Open menu</span>
            <Bars3Icon v-if="!open" class="block h-6 w-6" aria-hidden="true" />
            <XMarkIcon v-else class="block h-6 w-6" aria-hidden="true" />
          </DisclosureButton>
        </div>
        <!-- Profile dropdown -->
        <Menu as="div" class="relative ml-4 flex-shrink-0">
          <div>
            <MenuButton
              class="flex rounded-full bg-white focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2"
            >
              <span class="sr-only">Open user menu</span>
            </MenuButton>
          </div>
          <transition
            enter-active-class="transition ease-out duration-100"
            enter-from-class="transform opacity-0 scale-95"
            enter-to-class="transform opacity-100 scale-100"
            leave-active-class="transition ease-in duration-75"
            leave-from-class="transform opacity-100 scale-100"
            leave-to-class="transform opacity-0 scale-95"
          >
          </transition>
        </Menu>
      </div>
      <nav class="hidden lg:flex lg:space-x-8 lg:py-2" aria-label="Global">
        <NuxtLink
          ><button class="w-20 bg-green-400 h-7">
            <a href="https://grusvej.dk">Grusvej</a>
          </button></NuxtLink
        >
      </nav>
    </div>

    <DisclosurePanel as="nav" class="lg:hidden" aria-label="Global">
      <div class="space-y-1 px-2 pb-3 pt-2">
        <NuxtLink
          ><button class="w-20 bg-green-400 h-7">
            <a href="https://grusvej.dk">Grusvej</a>
          </button></NuxtLink
        >
      </div>
      <div class="border-t border-gray-200 pb-3 pt-4">
        <div class="flex items-center px-4">
          <!-- ... (your existing user information code) ... -->
        </div>
        <div class="mt-3 space-y-1 px-2">
          <NuxtLink
            v-for="item in userNavigation"
            :key="item.name"
            :to="item.href"
            class="block rounded-md px-3 py-2 text-base font-medium text-gray-500 hover:bg-gray-50 hover:text-gray-900"
            >{{ item.name }}</NuxtLink
          >
        </div>
      </div>
    </DisclosurePanel>
  </Disclosure>
</template>

<style>
.router-link-active {
  @apply bg-gray-100 text-gray-900;
}
</style>

<script setup>
import {
  Disclosure,
  DisclosureButton,
  DisclosurePanel,
  Menu,
  MenuButton,
  MenuItem,
  MenuItems,
} from "@headlessui/vue";
import { MagnifyingGlassIcon } from "@heroicons/vue/20/solid";
import { Bars3Icon, BellIcon, XMarkIcon } from "@heroicons/vue/24/outline";

const user = {
  name: "",
  email: "",
  imageUrl: "",
};
</script>
