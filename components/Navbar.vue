<template>
  <div class="bg-gray-900 text-gray-100 py-3.5 px-6 shadow">

    <!-- Mobile Menu -->
    <div class="md:hidden text-xl">
      <div class="flex justify-between">
        <a :href="home">Alpaq</a>
        <a @click="toggleMenu()">MENU</a>
      </div>
      <ul :class="{ 'hidden': !mobileMenuOpen }">
        <li v-for="link in links" :key="link.name">
          <a :href="link.link">{{ link.name }}</a>
        </li>
      </ul>
    </div>

    <!-- Desktop Menu -->
    <div class="hidden md:flex md:justify-between text-xl">
      <a :href="home">Alpaq</a>
      <ul class="md:flex">
        <li v-for="link in links" v-bind:key="link" class="md:mx-4">
          <a :href="link.link" class="hover:text-green-500">{{ link.name }}</a>
        </li>
      </ul>
    </div>
    
  </div>
</template>

<script>
export default {
  data() {
    return {
      home: "/",
      links: [
        { name: "Gallery", link: "/gallery" },
        { name: "News", link: "/news" },
        { name: "About", link: "/about" },
        { name: "Contact", link: "/contact" },
      ],
      mobileMenuOpen: false, // Track the state of the mobile menu
    };
  },
  methods: {
    toggleMenu() {
      this.mobileMenuOpen = !this.mobileMenuOpen;
    },
  },
};
</script>
