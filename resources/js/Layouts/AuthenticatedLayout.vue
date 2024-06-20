<script setup>
import { ref } from "vue";
import NavLink from "@/Components/NavLink.vue";
import SideLink from "@/Components/SideLink.vue";
import ApplicationLogo from "@/Components/ApplicationLogo.vue";
import ResponsiveNavLink from "@/Components/ResponsiveNavLink.vue";

const showingNavigationDropdown = ref(false);
const isSidebarOpen = ref(false);
</script>

<template>
  <div>
    <div class="min-h-screen bg-gray-100">
      <nav class="bg-white border-b border-gray-100">
        <!-- Primary Navigation Menu -->
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div class="flex justify-between h-16">
            <div class="flex">
              <!-- Navigation Links -->
              <div class="hidden space-x-8 sm:-my-px sm:ml-10 sm:flex">
                <ApplicationLogo :href="route('home')">
                  MegaGrand
                </ApplicationLogo>
              </div>
            </div>

            <div class="hidden sm:flex sm:items-center sm:ml-6">
              <!-- Settings Dropdown -->
              <div class="ml-3 relative">
                <NavLink :href="route('logout')" method="post" as="button">
                  Выйти
                </NavLink>
              </div>
            </div>

            <!-- Hamburger -->
            <div class="-mr-2 flex items-center sm:hidden">
              <button
                @click="showingNavigationDropdown = !showingNavigationDropdown"
                class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:bg-gray-100 focus:text-gray-500 transition duration-150 ease-in-out"
              >
                <svg
                  class="h-6 w-6"
                  stroke="currentColor"
                  fill="none"
                  viewBox="0 0 24 24"
                >
                  <path
                    :class="{
                      hidden: showingNavigationDropdown,
                      'inline-flex': !showingNavigationDropdown,
                    }"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M4 6h16M4 12h16M4 18h16"
                  />
                  <path
                    :class="{
                      hidden: !showingNavigationDropdown,
                      'inline-flex': showingNavigationDropdown,
                    }"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M6 18L18 6M6 6l12 12"
                  />
                </svg>
              </button>
            </div>
          </div>
        </div>

        <!-- Responsive Navigation Menu -->
        <div
          :class="{
            block: showingNavigationDropdown,
            hidden: !showingNavigationDropdown,
          }"
          class="sm:hidden"
        >
          <div class="pt-2 pb-3 space-y-1">
            <ResponsiveNavLink
              :href="route('home')"
              :active="route().current('home')"
            >
              Главная
            </ResponsiveNavLink>
            <ResponsiveNavLink
              :href="route('profile.edit')"
              :active="route().current('profile.edit')"
            >
              Профиль
            </ResponsiveNavLink>
            <ResponsiveNavLink
              :href="route('logout')"
              method="post"
              as="button"
            >
              Выйти
            </ResponsiveNavLink>
          </div>
        </div>
      </nav>
      <!-- Page Content -->
      <main class="max-w-7xl mx-auto mt-4 px-4 sm:px-6 lg:px-8">
        <div class="bg-white shadow-lg flex flex-col md:flex-row">
          <!-- Sidebar -->
          <div
            :class="{
              block: isSidebarOpen,
              hidden: !isSidebarOpen,
              'md:block': true,
            }"
            class="w-full md:w-1/6 p-4 md:p-6"
          >
            <div class="border border-gray-300 p-4 rounded-lg shadow-lg">
              <nav class="flex flex-col space-y-2">
                <SideLink
                  :href="route('home')"
                  :active="route().current('home')"
                  class="block text-gray-600 hover:text-gray-900"
                >
                  Главная
                </SideLink>
                <SideLink
                  :href="route('profile.edit')"
                  :active="route().current('profile.edit')"
                  class="block text-gray-600 hover:text-gray-900"
                >
                  Профиль
                </SideLink>
              </nav>
            </div>
          </div>

          <!-- Main content -->
          <div class="flex-1 p-4 md:p-6">
            <slot />
          </div>
        </div>
      </main>
    </div>
  </div>
</template>
