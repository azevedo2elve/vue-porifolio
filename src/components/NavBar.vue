<template>
  <nav class="bg-gray-800 text-white fixed w-full z-10 shadow-md">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between items-center h-16">
        <!-- Logo -->
        <div class="flex-shrink-0">
          \
          <img :src="require('@/assets/logo_twelve_square.png')" alt="Logo" class="h-10 w-10" />
        </div>

        <!-- Nav Links -->
        <div class="hidden md:flex space-x-4">
          <a href="#home" class="hover:text-gray-400">Home</a>
          <a href="#about" class="hover:text-gray-400">About</a>
          <a href="#skills" class="hover:text-gray-400">Skills</a>
          <a href="#projects" class="hover:text-gray-400">Projects</a>
          <a href="#contacts" class="hover:text-gray-400">Contacts</a>
        </div>

        <!-- Language Switcher -->
        <div class="hidden md:flex items-center">
          <button @click="toggleLanguage" class="hover:text-gray-400">
            {{ currentLanguage }}
          </button>
        </div>

        <!-- Mobile Menu Button -->
        <div class="md:hidden flex items-center">
          <button @click="toggleMenu" class="text-gray-300 hover:text-white focus:outline-none">
            <svg
              v-if="!isMenuOpen"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              class="w-6 h-6"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M3.75 5.25h16.5m-16.5 7.5h16.5m-16.5 7.5h16.5"
              />
            </svg>
            <svg
              v-else
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              class="w-6 h-6"
            >
              <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button>
        </div>
      </div>
    </div>

    <!-- Mobile Menu -->
    <div v-if="isMenuOpen" class="md:hidden bg-gray-700">
      <a href="#home" class="block px-4 py-2 hover:bg-gray-600">Home</a>
      <a href="#about" class="block px-4 py-2 hover:bg-gray-600">About</a>
      <a href="#skills" class="block px-4 py-2 hover:bg-gray-600">Skills</a>
      <a href="#projects" class="block px-4 py-2 hover:bg-gray-600">Projects</a>
      <a href="#contacts" class="block px-4 py-2 hover:bg-gray-600">Contacts</a>
      <button @click="toggleLanguage" class="block px-4 py-2 hover:bg-gray-600">
        {{ currentLanguage }}
      </button>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      isMenuOpen: false,
      currentLanguage: 'EN',
    }
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen
    },
    toggleLanguage() {
      this.currentLanguage = this.currentLanguage === 'EN' ? 'PT' : 'EN'
    },
  },
}
</script>

<style scoped>
nav {
  background-color: #1f2937; /* Tailwind's gray-800 */
  color: white;
}
</style>
