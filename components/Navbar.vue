<template>
  <div class="bg-gray-900 text-gray-100 py-3.5 px-6 shadow md:flex justify-between items-center">
    <div class="cursor-pointer">
      <h1 class="text-xl">Alpaq</h1>
    </div>
    <ul class="md:flex md:items-center">
      <li v-for="link in links" v-bind:key="link" class="md:mx-4">
        <a :href="link.link" class="text-xl hover:text-green-500">{{ link.name }}</a>
      </li>
    </ul>
  </div>
</template>

<script>
  const links = [
    { name: "Home", link: "/" },
    { name: "Gallery", link: "/gallery" },
    { name: "News", link: "/news" },
    { name: "About", link: "/about" },
    { name: "Contact", link: "/contact" },
  ];

  export default {
    setup() {
      return {
        links,
      };
    },
  };
</script>
